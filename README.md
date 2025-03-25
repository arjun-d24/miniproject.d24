{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": []
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "code",
      "execution_count": 4,
      "metadata": {
        "id": "fFOOAR1u5ZrY"
      },
      "outputs": [],
      "source": [
        "class BankAccount:\n",
        "  def __init__(self, account_number, pin, balance=0):\n",
        "    self.account_number=account_number\n",
        "    self.pin = pin\n",
        "    self.balance = balance"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "def deposit(self, amount):\n",
        "        if amount > 0:\n",
        "            self.balance += amount\n",
        "            print(f\"Deposited ${amount}. New balance is ${self.balance}.\")\n",
        "        else:\n",
        "            print(\"Deposit amount must be positive.\")"
      ],
      "metadata": {
        "id": "6Ut1hA5D7hZr"
      },
      "execution_count": 8,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "def withdraw(self, amount):\n",
        "        if amount > 0:\n",
        "            if amount <= self.balance:\n",
        "                self.balance -= amount\n",
        "                print(f\"Withdrew ${amount}. New balance is ${self.balance}.\")\n",
        "            else:\n",
        "                print(\"Insufficient funds.\")\n",
        "        else:\n",
        "            print(\"Withdrawal amount must be positive.\")"
      ],
      "metadata": {
        "id": "BxLRbdh_8bUJ"
      },
      "execution_count": 9,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        " def get_balance(self):\n",
        "        return self.balance"
      ],
      "metadata": {
        "id": "pEHioDWg9x0p"
      },
      "execution_count": 14,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "accounts = {\n",
        "    '123456': BankAccount('123456', '1234', 500),\n",
        "    '654321': BankAccount('654321', '4321', 1000)\n",
        "}"
      ],
      "metadata": {
        "id": "WpWZkFvJ900I"
      },
      "execution_count": 15,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "def login():\n",
        "    print(\"Welcome to the Bank System!\")\n",
        "    account_number = input(\"Enter your account number: \")\n",
        "    pin = input(\"Enter your PIN: \")\n",
        "\n",
        "    if account_number in accounts and accounts[account_number].pin == pin:\n",
        "        print(\"Login successful!\")\n",
        "        return accounts[account_number]\n",
        "    else:\n",
        "        print(\"Invalid account number or PIN.\")\n",
        "        return None\n"
      ],
      "metadata": {
        "id": "d88xwUw79nTb"
      },
      "execution_count": 13,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "def main():\n",
        "    account = login()\n",
        "\n",
        "    if account:\n",
        "        while True:\n",
        "            print(\"\\nOptions:\")\n",
        "            print(\"1. Deposit\")\n",
        "            print(\"2. Withdraw\")\n",
        "            print(\"3. Check Balance\")\n",
        "            print(\"4. Logout\")\n",
        "            choice = input(\"Enter your choice: \")\n",
        "\n",
        "            if choice == '1':\n",
        "                amount = float(input(\"Enter amount to deposit: \"))\n",
        "                account.deposit(amount)\n",
        "            elif choice == '2':\n",
        "                amount = float(input(\"Enter amount to withdraw: \"))\n",
        "                account.withdraw(amount)\n",
        "            elif choice == '3':\n",
        "                print(f\"Your balance is ${account.get_balance()}.\")\n",
        "            elif choice == '4':\n",
        "                print(\"Logged out successfully.\")\n",
        "                break\n",
        "            else:\n",
        "                print(\"Invalid choice. Please try again.\")\n",
        "\n",
        "if __name__ == \"__main__\":\n",
        "    main()"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "bes4Zhla95dn",
        "outputId": "16e7f53b-5798-4934-abad-a27061425904"
      },
      "execution_count": 18,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Welcome to the Bank System!\n",
            "Enter your account number: 123456\n",
            "Enter your PIN: 1234\n",
            "Login successful!\n",
            "\n",
            "Options:\n",
            "1. Deposit\n",
            "2. Withdraw\n",
            "3. Check Balance\n",
            "4. Logout\n",
            "Enter your choice: 4\n",
            "Logged out successfully.\n"
          ]
        }
      ]
    }
  ]
}
