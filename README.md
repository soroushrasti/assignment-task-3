### Problem: Implement Rate Limiting for API Requests

**Description:**

Please implement a rate-limiting feature for an API to ensure that users do not exceed a certain number of requests within a given time window. 
The rate-limiting logic should allow users to make requests, but restrict further requests if they exceed the allowed number of requests per time window.

**Requirements**:
- The `allow_request()` method checks if the user can make a request based on the rate limit and the time window.
- The `make_request()` method processes the request by returning a simple message if allowed, and denying request by giving a message of the limit is exceeded.

**Tips**:
- Number of requests should be tracked for each user_name
- The `allow_request()` method should return `True` if the request is allowed, and `False` if the limit is exceeded.
- The rate-limiter should efficiently track and manage requests within a fixed time window.
- You need to clean up Clean up expired requests every time
- Implement RateLimiter with two arguments: max_requests and time_window (in seconds) 
- make_request function get user_name as input

**Example Test**:
```python
Import time
rate_limiter = RateLimiter(max_requests=3, time_window=10)

# User makes requests
print(rate_limiter.make_request("userA"))  #response: Request processed
print(rate_limiter.make_request("userA"))  #response: Request processed
print(rate_limiter.make_request("userA"))  #response: Request processed
print(rate_limiter.make_request("userA"))  #response: Deniend, rate limit exceeded

# After 10 seconds, UserA can make requests again
time.sleep(10)
print(rate_limiter.make_request("userA"))  #response: Request processed
```
