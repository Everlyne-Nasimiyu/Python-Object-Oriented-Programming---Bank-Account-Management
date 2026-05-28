# Python Object-Oriented Programming: Bank Account Management

This project demonstrates fundamental concepts of Object-Oriented Programming (OOP) in Python by implementing a simple bank account management system. It features a `Account` class that allows users to create bank accounts, deposit funds, withdraw money, and check their account balance.

## Features

- **Account Creation**: Initialize bank accounts with an account number, account holder name, and an optional initial balance.
- **Deposit Funds**: Add money to an account.
- **Withdraw Funds**: Remove money from an account, with checks for sufficient balance.
- **Check Balance**: View the current balance of an account.

## Getting Started

To use this project, simply run the Python code. No special installation is required beyond a standard Python environment.

### Prerequisites

- Python 3.x

### Usage

Here's how to create an account and interact with it:

```python
class Account:
  def __init__(self, account_number: str, account_holder: str, account_balance: float = 0.0):
    self.account_number = account_number
    self.account_holder = account_holder
    self.account_balance = account_balance
    print(f"Account {self.account_number} created for {self.account_holder} with account_balance ${self.account_balance:.2f}.")

  def deposit(self, amount: float):
    if amount > 0:
      self.account_balance += amount
      print(f"Deposited amount ${amount:.2f}. New balance: ${self.account_balance:.2f}.")
    else:
      print("Deposit amount must be positive.")

  def withdraw(self, amount: float):
    if amount <= 0:
      print("Withdrawal amount must be positive.")
    elif self.account_balance >= amount:
      self.account_balance -= amount
      print(f"Withdrew amount ${amount:.2f}. New balance: ${self.account_balance:.2f}.")
    else:
      print(f"Insufficient funds. Current balance: ${self.account_balance:.2f}. Attempted withdrawal: ${amount:.2f}.")

  def check_balance(self) -> float:
    print(f"Current balance for account {self.account_number}: ${self.account_balance:.2f}.")
    return self.account_balance

# Create an account
my_account = Account("123456789", "John Doe", 500.00)

# Deposit money
my_account.deposit(100.00)

# Withdraw money
my_account.withdraw(75.00)

# Check balance
my_account.check_balance()

# Attempt to over-withdraw
my_account.withdraw(1000.00)
```

### Account Class

#### `__init__(self, account_number: str, account_holder: str, account_balance: float = 0.0)`

The constructor for the `Account` class.

-   `account_number`: A unique string identifier for the account.
-   `account_holder`: The name of the account holder.
-   `account_balance`: The initial balance of the account (defaults to 0.0).

#### `deposit(self, amount: float)`

Deposits a specified amount into the account.

-   `amount`: The amount of money to deposit. Must be positive.

#### `withdraw(self, amount: float)`

Withdraws a specified amount from the account.

-   `amount`: The amount of money to withdraw. Must be positive and less than or equal to the current balance.

#### `check_balance(self) -> float`

Prints and returns the current balance of the account.

## Author

[Your Name/GitHub Username] - *Initial Work*

```
