# Read 36
# Cognito and Authentication

- To setup and configure your application with Amplify Auth and go through a simple api to check the current auth session
- Amazon Amplify  comes with the Amazon Cognito for authentication
- Cognito is supposed to be quick and easy to set up authentication for your app
- You can set up social log in
- It supports OAuth 2.0, SAML 2.0 and Open ID connect
- You can implement the following to get it set up
- You start with the CLI and inputting the commands
- add the dependencies
- Cognito is in  compliance with security and compliance to laws on personal information
````
commands: 
- amplify add auth
 - amplify push
````

````
dependencies {
    implementation 'com.amplifyframework:aws-auth-cognito:1.35.4'
}
````
- Initalize
- Add this line, to include the Auth plugin.
````
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.configure(getApplicationContext());
````
- Current auth session
````
Amplify.Auth.fetchAuthSession(
    result -> Log.i("AmplifyQuickstart", result.toString()),
    error -> Log.e("AmplifyQuickstart", error.toString())
);
````


### Resorces 
- [AWS Cognito](https://docs.amplify.aws/lib/auth/getting-started/q/platform/android/)


