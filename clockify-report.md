# No rate limiting leads to Email triggering
vulnerability name: No rate limiting leads to Email triggering
## Description
A rate-limiting algorithm is used to check if the user session (or IP address) has to be limited based on the information in the session cache.
In case a client made too many requests within a given timeframe, HTTP-Servers can respond with status code 429: Too Many Requests.

I have identified that when verifying email, the request has no rate limit which then can be used to loop through one request. Which can be annoying to the root users sending a mass password to one email.
