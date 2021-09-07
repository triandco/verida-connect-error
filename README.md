## Summary
We encountered an error when trying to use @verida/datastore version 0.7.4

```
index.js:64 Uncaught (in promise) Error: A password is required for encryption or decryption.
```

## Reproduction

1. Install dependencies
```
npm install
```

2. Start development server
```
npm run dev
```

3. Open web browser and navigate to the development server at [http://localhost:8080](http://localhost:8080)

4. Click on connect button to connect

5. Login with metamask

## Expectation

Connect to app using metamask successfully


## Actual

Receiving message in the browser console
```
index.js:64 Uncaught (in promise) Error: A password is required for encryption or decryption.
```

This error seems to be thrown from the crypto-pouch > garbados-crypt package