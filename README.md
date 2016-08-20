# whattopaytowhom
Calculate repayments of a number of people to reach average after initial unequal payments.

### Example usage
Initial payments are provided with a data file. For instance, put the following in `initial_payments.txt`:

```
Name1 Food 4000
Name2 Drinks 2000
Name3 Food 1000
Name1 Transportation 2000
```

Here in each row the first column represents a person and the last column represents a payment made by that person. There may be multiple rows that indicate different payments from the same person. Now run `whattopaytowhom` passing `initial_payments.txt` as command line argument:

`./whattopaytowhom initial_payments.txt`

The result indicates who should pay what amount to whom so that in the end the initial total amount is equally shared among all:

```
Initially
  Name1 payed 6000.00
  Name2 payed 2000.00
  Name3 payed 1000.00

Total: 9000.00

Each person should have paid 3000.00, but that didn't work

Now
  Name2 should pay 1000.00 to Name1
  Name3 should pay 2000.00 to Name1
```

We can also give the money unit as a command line argument:

`./whattopaytowhom initial_payments.txt yen`

which results in:

```
Initially
  Name1 payed 6000.00 yen
  Name2 payed 2000.00 yen
  Name3 payed 1000.00 yen

Total: 9000.00 yen

Each person should have paid 3000.00 yen, but that didn't work

Now
  Name2 should pay 1000.00 yen to Name1
  Name3 should pay 2000.00 yen to Name1
```

#### Data with single column
If the initial payments data file has a single column, then each row is considered to be the initial payment of a different person. For instance, if the `initial_payments_single_column.txt` is given by:

```
1000
3000
5000
2000
6000
```

then `./whattopaytowhom initial_payments_single_column.txt` returns:

```
Initially
  Person #1 payed 1000.00
  Person #2 payed 3000.00
  Person #3 payed 5000.00
  Person #4 payed 2000.00
  Person #5 payed 6000.00

Total: 17000.00

Each person should have paid 3400.00, but that didn't work

Now
  Person #1 should pay 2400.00 to Person #5
  Person #2 should pay 400.00 to Person #3
  Person #4 should pay 1200.00 to Person #3
  Person #4 should pay 200.00 to Person #5
```
