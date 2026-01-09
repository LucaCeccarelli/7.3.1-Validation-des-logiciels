# Table of the metrics across the classes

| Class              | WMC | CBO | LCOM | LOC | Quick Notes |
|--------------------|:---:|:---:|:----:|:---:|:-----------:|
| BankAccount        | 21  |  2  | 46   | 460 |      -      |
| Person             | 23  |  3  | 79   | 325 |      -      |
| BankAccountApp     |  2  |  3  | 1    | 491 |      -      |
| Bank               | 14  |  4  | 0    | 413 |      -      |

## Which class has the highest WMC?
The Person class has the highest WMC with a value of 23.
## Which class has the highest CBO?
The Bank class has the highest CBO with a value of 4.
## Which one class would you worry about most for future maintenance, and why?
I would worry most about the Person class for future maintenance. 
It has the highest WMC (23) and a high LCOM (79), indicating that it has many methods and a significant lack of cohesion among them. 
This combination suggests that the class is complex and may be difficult to maintain or modify without introducing errors.
And as the CBO is also relatively high (3), it indicates that the class is coupled with other classes, which can further complicate maintenance tasks.
