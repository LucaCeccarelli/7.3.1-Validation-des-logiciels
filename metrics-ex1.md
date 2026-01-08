# Metrics
Metrics command : 
```bash
java -jar /home/luca/Downloads/ckjm_ext.jar target/classes/bankAccountApp/*.class
```
Metrics result :
```md
WMC, DIT, NOC, CBO, RFC, LCOM, Ca, Ce, NPM, LCOM3, LOC, DAM, MOA, MFA, CAM, IC, CBM and AMC
```
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

bankAccountApp.ACHService 2 1 0 1 2 1 1 0 2 2.0000 2 0.0000 0 0.0000 0.8333 0 0 0.0000
 ~ public abstract boolean registerAccount(int, int, int, int): 1
 ~ public abstract boolean transferAmount(int, int, int, int, float): 1

bankAccountApp.Person 23 1 0 3 39 79 3 0 21 0.7626 325 0.8889 0 0.0000 0.3565 0 0 12.7391
 ~ public void <init>(String accountHolder): 3
 ~ public void <init>(String newName, char newGender, int newAge, float newHeight): 1
 ~ public float getWeight(): 1
 ~ public void setAge(int newAge): 2
 ~ public String getEyeColor(): 1
 ~ public void setName(String newName): 1
 ~ public String getName(): 1
 ~ private void validate(): 1
 ~ public String getEmail(): 1
 ~ public void setEmail(String email): 1
 ~ public void setHairColor(String newHairColor): 5
 ~ public void setWeight(float newWeight): 1
 ~ public String getHairColor(): 1
 ~ public String toString(): 1
 ~ public void setHeight(float height): 1
 ~ public int getAge(): 1
 ~ public void <init>(String newName, char newGender, int newAge, float newWeight, float newHeight, String newHairColor, String newEyeColor, String newEmail): 1
 ~ public void setGender(char newGender): 2
 ~ public char getGender(): 1
 ~ public void setEyeColor(String newEyeColor): 1
 ~ private boolean validateGender(char value): 5
 ~ public void <init>(): 1
 ~ public float getHeight(): 1

bankAccountApp.BankAccountApp 2 1 0 3 36 1 0 3 2 2.0000 491 0.0000 0 0.0000 0.5000 0 0 244.5000
 ~ public static void main(String[] args): 40
 ~ public void <init>(): 1

bankAccountApp.ACHServiceImpl 3 1 0 2 4 3 1 1 3 2.0000 10 0.0000 0 0.0000 0.6667 0 0 2.3333
 ~ public boolean registerAccount(int fromAccountNumber, int fromRoutingNumber, int destinationBank, int toAccountNumber): 1
 ~ public void <init>(): 1
 ~ public boolean transferAmount(int fromAccountNumber, int fromRoutingNumber, int destinationBank, int toAccountNumber, float amount): 1

bankAccountApp.Bank 14 1 0 4 44 0 2 3 12 0.8333 413 1.0000 0 0.0000 0.3286 0 0 28.0714
 ~ public double getMinimumBalance(): 4
 ~ public void saveAccounts(bankAccountApp.Bank accManager): 8
 ~ public boolean registerAccount(int fromAccountNumber, int fromRoutingNumber, int destinationBank, int toAccountNumber): 1
 ~ public double getMaximumBalance(): 3
 ~ public void deleteAccount(int accountNumber): 3
 ~ public String convertToText(): 2
 ~ public int addAccount(bankAccountApp.BankAccount acc, int isLoadAccount): 4
 ~ protected int getAccountsLoaded(): 1
 ~ public java.util.ArrayList getAccounts(): 1
 ~ public boolean transferAmount(int fromAccountNumber, int fromRoutingNumber, int destinationBank, int toAccountNumber, float amount): 1
 ~ public bankAccountApp.BankAccount findAccount(int accountNumber): 4
 ~ public double getAverageBalance(): 2
 ~ public void <init>(): 1
 ~ protected void setAccountsLoaded(int accountsLoaded): 1
```
## All computed metrics
| Class              | WMC | DIT | NOC | CBO | RFC | LCOM | Ca | Ce | NPM | LCOM3  | LOC | DAM    | MOA | MFA    | CAM    | IC | CBM | AMC      |
|--------------------|:---:|:---:|:---:|:---:|:---:|:----:|:--:|:--:|:---:|:------:|:---:|:------:|:---:|:------:|:------:|:--:|:---:|:--------:|
| BankAccount        | 20  | 1   | 0   | 3   | 43  | 44   | 2  | 2  | 18  | 0.6908 | 462 | 1.0000 | 1   | 0.0000 | 0.2917 | 0  | 0   | 21.7000  |
| ACHService         | 2   | 1   | 0   | 1   | 2   | 1    | 1  | 0  | 2   | 2.0000 | 2   | 0.0000 | 0   | 0.0000 | 0.8333 | 0  | 0   | 0.0000   |
| Person             | 23  | 1   | 0   | 3   | 39  | 79   | 3  | 0  | 21  | 0.7626 | 325 | 0.8889 | 0   | 0.0000 | 0.3565 | 0  | 0   | 12.7391 |
| BankAccountApp     | 2   | 1   | 0   | 3   | 36  | 1    | 0  | 3  | 2   | 2.0000 | 491 | 0.0000 | 0   | 0.0000 | 0.5000 | 0  | 0   | 244.5000 |
| ACHServiceImpl     | 3   | 1   | 0   | 2   | 4   | 3    | 1  | 1  | 3   | 2.0000 | 10  | 0.0000 | 0   | 0.0000 | 0.6667 | 0  | 0   | 2.3333  |
| Bank               | 14  | 1   | 0   | 4   | 44  | 0    | 2  | 3  | 12  | 0.8333 | 413 | 1.0000 | 0   | 0.0000 | 0.3286 | 0  | 0   | 28.0714 |

## Requested metrics
| Class             | WMC | LOC |                                        Short Description of responsibility                                        |
|-------------------|:---:|:---:|:-----------------------------------------------------------------------------------------------------------------:|
| BankAccount       | 20  | 462 | Represents a single bank account, storing account data and handling deposits/withdrawals plus text serialization. |
| Person            | 23  | 325 |              Represents an account holder’s personal data with validation and parsing/serialization.              |
| BankAccountApp    | 2   | 491 |            Command-line entry point that drives user interaction and orchestrates account operations.             |
| Bank              | 14  | 413 |    Manages a collection of accounts, provides aggregate calculations, and handles persistence/transfer hooks.     |

### Do you feel its size roughly matches its responsibility?
Mostly no. From the Requested metrics table, BankAccountApp is huge (LOC 491) despite a tiny WMC (2), so its size doesn’t match its narrow entry‑point responsibility. BankAccount (LOC 462, WMC 20), Person (LOC
325, WMC 23), and Bank (LOC 413, WMC 14) are large but their responsibilities involve state plus multiple behaviors, so those are closer to matching.