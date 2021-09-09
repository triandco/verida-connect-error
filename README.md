## Summary
Verida app user.getAppConfig() return false instead of configuration object when initiated without specifying appName using Verida.setConfig()

## Reproduction
1. Generate DID and signing signature from another app. In my case, I use @verida/vault-auth-client
2. Update DID and SIGNATURE constant in App.svelte
3. run npm install to restore dependencies
4. open https://localhost:8080 in your browser 
5. Hit login to sign in and get configuration object

## Expected
Configuration object printed on the screen

## Actual 
Configuration object is false

## Workaround
Specify appname using Verida.setConfig({appName: "someappname"})
```typescript
Verida.setConfig({ appName: appname });
```

