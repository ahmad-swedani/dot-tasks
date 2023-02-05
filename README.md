- [x] Add connect account state api to display in Bank info

add more info for the bank info instead of just return an empty object if the the account is still restricted the new info are the following:
1. `payouts_enabled`
1. `details_submitted`
1. `charges_enabled`
1. `external_accounts_count`

API Endpoint: `GET /users/bank_info/`
if the account still restricted: the response will be like this:
```json
{
    "payouts_enabled": false, // new
    "details_submitted": false, // new
    "charges_enabled": true, // new
    "external_accounts_count": 0 // new
}
```
---

if the account is enabled: the response will be like this:
```json
{
    "id": "ba_1MXo4WIc8s02NTBEtzwhQ0Xc",
    "object": "bank_account",
    "account": "acct_1MXmufIc8s02NTBE",
    "account_holder_name": "Hadeel Hisham Aljarbouah",
    "account_holder_type": "individual",
    "account_type": null,
    "available_payout_methods": [
        "standard"
    ],
    "bank_name": "STRIPE TEST BANK",
    "country": "JO",
    "currency": "jod",
    "default_for_currency": true,
    "fingerprint": "yC8DNh2IszYrghHw",
    "last4": "5678",
    "metadata": {
        "email": "swedani390@gmail.com"
    },
    "routing_number": "AAAAJOJOXXX",
    "status": "new",
    "payouts_enabled": true, // new
    "details_submitted": true, // new
    "charges_enabled": true, // new
    "external_accounts_count": 1 // new
}
```

- [ ] Refund state API (Success, Pending, ..)

- [ ] Delete attachment indicator

- [x] Allow adding or rescheduling sessions for the last invalid 15 mins

- [ ] Receivables Amount after the payout should turn into 0
    - ***will talk to Bakri about the way of process_user_payouts***

- [x] Add a hard coded transaction purpose (Consultation fees)

- [x] Refund fees? Apply fees?

    - > no fees for refunds

- [ ] Reflect client’s time zone in the Session link

- [ ] Add 5 more business days to transform a state to paid (because it might transfer to failed)

- [ ] Stripe: Two balances, JOD, USD??

- [x] No of clients reflects (confirmed+active+done+collected) NOT awaiting payments

- [ ] Add country and currency api upon signup

- [ ] JSON file (list of banks per country)