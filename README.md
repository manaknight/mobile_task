# react_native_task
Task 1: Oct 18 2021
1. Initialize an app. Connect the app with splash screen and icon. Configure app to use any one of the custom font globally.

2. Implement authentication screens(login, signup, forgot password, validate password reset confirmation code and reset password) and connect to the REST API. Domain for this is https://vyod.manaknightdigital.com

- Do not use any UI library. Do form state management without any library.
- Login screen takes email and password. Do all the basic validation on client side and display proper error message if theres error from the API. Display the error message either in toast, custom dialog or native alert. API endpoint is /member/api/login. Request body are email, password.
- Register screen takes email, password, first_name, last_name(and code for this VOYD app). Validation similar to Login screen should be applied. API endpoint is /member/api/register. Request body are email, password, first_name, last_name, code.
- Forgot password screen should ask for email. User cannot request for password reset if their account is not verified.If the account is not verified display a dialog that has a button to request for resend aacount verification email. API endpoint is /member/api/verify-account, Request body is email. If the account is verified and email exists on our system, they will get a password reset validation code in their inbox. Navigate the user to screen that validates this code. API endpoint is /member/api/forgot. Request body is email.
- On validate reset password code make a 8 digit otp input field using package "@twotalltotems/react-native-otp-input". The purpose of this package is to detect otp automatically when we use SMS system. When code is valid navigate user to final reset password screen. API endpoint is /member/api/validate-reset-code. Request body are email, code
- On reset password screen make 2 input type password fields and do all the client side validation. Password should atleast be 6 digits long. API endpoint is /member/api/reset-password. Request body are email, code and password.

3. After the user sucessfully logs in or signs up implement a switch naviagtor to switch to screens to be shown after authentication. In this app it is the 'Home' screen.

4. Persist the token that we receive after successfully authenticating using AsyncStorage. You can persist other data using Redux or make custom useContext, useReducer and AsyncStorage mechanism.

5. Implement the UI of dashboard and connect the drawer on the left side.
