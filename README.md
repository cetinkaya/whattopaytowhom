# whattopaytowhom
Calculate repayments of a number of people to reach average after initial unequal payments.

Initial payments are provided with a data file. For instance, put the following in `initial_payments.txt`:

```
Name1 Food 4000
Name2 Drinks 2000
Name3 Food 1000
Name1 Transportation 2000
```

Run `whattopaytowhom` passing `initial_payments.txt` as command line argument:

`./whattopaytowho initial_payments.txt`

The result indicates who should pay what amount to whom so that in the end initial total amount is equally shared among people:

```
Initially
  Name1 payed 6000.00000
  Name2 payed 2000.00000
  Name3 payed 1000.00000

Total: 9000.00000

Each person should have paid 3000.00000, but that didn't work

Now
  Name2 should pay 1000.00000 to Name1
  Name3 should pay 2000.00000 to Name1
```

We can also give the money unit as a command line argument:

`./whattopaytowho initial_payments.txt yen`

which results in:

```
Initially
  Name1 payed 6000.00000 yen
  Name2 payed 2000.00000 yen
  Name3 payed 1000.00000 yen

Total: 9000.00000 yen

Each person should have paid 3000.00000 yen, but that didn't work

Now
  Name2 should pay 1000.00000 yen to Name1
  Name3 should pay 2000.00000 yen to Name1
```
