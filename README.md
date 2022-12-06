#Account class and checking_account instance, complete with public and private methods.

#Include a deposit method that lets users add money to their accounts
#Include error checking that prevents users from overdrawing their accounts
#Create CheckingAccounts or SavingsAccounts that inherit from Account

class Account
  attr_reader :name
  attr_reader :balance

  def initialize(name, balance=100)
    @name = name
    @balance = balance
  end

  private
  def pin
  @pin = 1234
  end

  private
  def pin_error
  return "Access denied: incorrect PIN."
  end

  public
  def display_balance(pin_number)
    if pin_number == pin
      puts "Balance: #{@balance}."
    else 
      puts pin_error
    end
  end

  public
  def withdraw(pin_number, amount)
     if pin_number == pin
     @balance = @balance - amount
       puts "Withdrew #{amount}. New balance: $#{@balance}." 
    else 
      puts pin_error
    end
  end

end

checking_account = Account.new("Kyle", 1000)
puts checking_account.pin


-----------------------------------------------------------------
