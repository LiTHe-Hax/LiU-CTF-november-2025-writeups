To solve the challenge you need to observe that new users are given a numerical id which is sent in the json body when making requests to /profile. 
Change the number sent and you will try to get another users profile, there is also an authentication check against the cookie, however the cookie 
is very simply MD5(username) which can be forged and sent with the request to access the right users profile (Torbjörn) which is user 4. 
