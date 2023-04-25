#  No rate limiting leads to email triggering

A little bit about Rate Limit:
A rate-limiting algorithm is used to check if the user session (or IP address) has to be limited based on the information in the session cache.
In case a client made too many requests within a given timeframe, HTTP-Servers can respond with status code 429: Too Many Requests.
## Description:-
I have identified that when verifying email, the request has no rate limit which then can be used to loop through one request. Which can be annoying to the root users sending a mass password to one email.

Steps to reproduce:

1. Go to this link https://www.hunkemoller.com/
2. And create an account using your email address
3. After creating your account go to the forgot password page
4. Enter your email address  
5. Click send and intercept the request and  Now Send This Request To Intruder And Repeat It 1000 or n number of times By Fixing Any Arbitrary Payload Which Doesn't No Effect Request I Choose Accept-Language: en-US, en;q=0.5 $1$
6. See You Will Get 200 ok Status Code & 1000+ ,  n number of emails In Your INBOX
7. See It Is Resulting In Mass Mailing Or Email Bombing To Your Users Which Is Bad For Business Impact.

  
Solution -
I Will Recommend You To Add A ReCaptcha & Sort Of Something Which Requires Manual Human Interaction To Proceed Like You Can Add Captcha Like 2+2=___ so that it cannot be brute-forced and you also can have a limit at the backend for a particular number up to 5 times a day user can request verify Email or Link something like that will prevent you from someone exploiting this vulnerability
  
POC- Attached Below
Impact
If You Are Using Any Email Service Software API Or Some Tool Which Costs You For Your Email This Type Of Attack Can Result from You In Financial Lose And It Can Also Slow Down Your Services It Can Take Bulk Of Storage In Sent Mail Although If Users Are Affected By This Vulnerability They Can Stop Using Your Services Which Can Lead To Business Risk.
vulnerability name: No rate limiting leads to email triggering

A little bit about Rate Limit:
A rate-limiting algorithm is used to check if the user session (or IP address) has to be limited based on the information in the session cache.
In case a client made too many requests within a given timeframe, HTTP-Servers can respond with status code 429: Too Many Requests.
## Description:-
I have identified that when verifying email, the request has no rate limit which then can be used to loop through one request. Which can be annoying to the root users sending a mass password to one email.
