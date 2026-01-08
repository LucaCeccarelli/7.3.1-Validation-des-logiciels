# Metrics 
```bash
bankAccountApp.BankAccount 20 1 0 3 43 44 2 2 18 0.6908 462 1.0000 1 0.0000 0.2917 0 0 21.7000
 ~ public void setWithdrawLimit(double withdrawLimit): 1
 ~ public void <init>(int accountNumber, double balance, double withdrawLimit, String dateCreated, String accountHolder): 1
 ~ public String convertToText(bankAccountApp.BankAccount tmp): 1
 ~ public void setAccountHolder(bankAccountApp.Person accountHolder): 2
 ~ public double getBalance(): 1
 ~ public int getAccountNumber(): 1
 ~ public void <init>(double newInitMoneyAmount, double newWithdrawlimit, String newDateCreated, bankAccountApp.Person initHolder): 1
 ~ public String getDateCreated(): 1
 ~ public String toString(): 1
 ~ public void depositMoney(double depositAmount): 2
 ~ public double getInitMoneyAmount(): 1
 ~ public double getWithdrawLimit(): 1
 ~ private void setDateCreated(String dateCreated): 1
 ~ public double getAmountWithdrawn(): 1
 ~ public int loadFromText(String text): 8
 ~ public void <init>(): 1
 ~ public void setAccountNumber(int accNumber): 1
 ~ private void setBalance(double balance): 1
 ~ public bankAccountApp.Person getAccountHolder(): 1
 ~ public boolean withdrawMoney(double withdrawAmount): 5
```

## Chosen method
### Cyclomatic complexity value
```bash
 ~ public boolean withdrawMoney(double withdrawAmount): 5
```
Cyclomatic complexity is 5
### Identity decision points
```java
public boolean withdrawMoney(double withdrawAmount) {
	if (withdrawAmount >= 0 && balance >= withdrawAmount && withdrawAmount < withdrawLimit
			&& withdrawAmount + amountWithdrawn <= withdrawLimit) { // Decision 1
		balance = balance - withdrawAmount;
		success = true;
		amountWithdrawn += withdrawAmount;
	} else {    // Decision 2
		success = false;
	}
	return success;
}
```
### Which part would you extract into a helper method?
I would extract the condition inside the first `if` :
``withdrawAmount >= 0 && balance >= withdrawAmount && withdrawAmount < withdrawLimit && withdrawAmount + amountWithdrawn <= withdrawLimit``
And removing the condition `withdrawAmount < withdrawLimit` that can be confirmed later by doing `amountWithdrawn <= withdrawLimit`
### What name would you give this helper?
I would name it `canWithdraw`

#### Bonus
##### Refactor proposed
```java
public boolean withdrawMoney(double withdrawAmount) {
    if (!canWithdraw(withdrawAmount)){
        return false;
    }
    balance = balance - withdrawAmount;
    amountWithdrawn += withdrawAmount;
    return true;
}

private boolean canWithdraw(double withdrawAmount) {
    return withdrawAmount >= 0 && balance >= withdrawAmount && withdrawAmount + amountWithdrawn <= withdrawLimit;
}
```
##### New metrics
```bash
java -jar /home/luca/Downloads/ckjm_ext.jar target/classes/bankAccountApp/BankAccount.class 
```
```bash
bankAccountApp.BankAccount 21 1 0 2 44 46 0 2 18 0.6938 460 1.0000 0 0.0000 0.2937 0 0 20.5238
 ~ public void setWithdrawLimit(double withdrawLimit): 1
 ~ public void <init>(int accountNumber, double balance, double withdrawLimit, String dateCreated, String accountHolder): 1
 ~ public String convertToText(bankAccountApp.BankAccount tmp): 1
 ~ public void setAccountHolder(bankAccountApp.Person accountHolder): 2
 ~ public double getBalance(): 1
 ~ public int getAccountNumber(): 1
 ~ public void <init>(double newInitMoneyAmount, double newWithdrawlimit, String newDateCreated, bankAccountApp.Person initHolder): 1
 ~ public String getDateCreated(): 1
 ~ public String toString(): 1
 ~ public void depositMoney(double depositAmount): 2
 ~ public double getInitMoneyAmount(): 1
 ~ public double getWithdrawLimit(): 1
 ~ private void setDateCreated(String dateCreated): 1
 ~ public double getAmountWithdrawn(): 1
 ~ public int loadFromText(String text): 8
 ~ public void <init>(): 1
 ~ private boolean canWithdraw(double withdrawAmount): 4
 ~ public void setAccountNumber(int accNumber): 1
 ~ private void setBalance(double balance): 1
 ~ public bankAccountApp.Person getAccountHolder(): 1
 ~ public boolean withdrawMoney(double withdrawAmount): 2
```
###### Relevant metrics
```bash
 ~ private boolean canWithdraw(double withdrawAmount): 4
 ~ public boolean withdrawMoney(double withdrawAmount): 2
```