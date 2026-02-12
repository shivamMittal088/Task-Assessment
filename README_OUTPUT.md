# Command Outputs

Below are the terminal commands and outputs for Tasks 1-4.

## Task 1: Fix Login
**Command:**
```bash
curl -X POST http://localhost:3000/auth/login -H "Content-Type: application/json" -d '{"email":"shivamofficialsm@gmail.com","password":"password123"}'
```
**Output:**
**{"message":"OTP sent","loginSessionId":"ex7mqj"}**

## Task 2: Fix OTP Verification
**Command:**
```bash
curl -c cookies.txt -X POST http://localhost:3000/auth/verify-otp -H "Content-Type: application/json" -d '{"loginSessionId":"ex7mqj","otp":"543964"}'
```
**Output:**
**{"message":"OTP verified","sessionId":"ex7mqj"}**

## Task 3: Fix Token Generation
**Command:**
```bash
curl -b cookies.txt -X POST http://localhost:3000/auth/token
```
**Output:**
**{"access_token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InNoaXZhbW9mZmljaWFsc21AZ21haWwuY29tIiwic2Vzc2lvbklkIjoiZXg3bXFqIiwiaWF0IjoxNzcwOTMyMjI4LCJleHAiOjE3NzA5MzMxMjh9.sKSLectFIlsTRGipVvrZKpuy7KwNtb18qd9CRq29UFc","expires_in":900}**

## Task 4: Fix Protected Route Access
**Command:**
```bash
curl -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InNoaXZhbW9mZmljaWFsc21AZ21haWwuY29tIiwic2Vzc2lvbklkIjoiZXg3bXFqIiwiaWF0IjoxNzcwOTMyMjI4LCJleHAiOjE3NzA5MzMxMjh9.sKSLectFIlsTRGipVvrZKpuy7KwNtb18qd9CRq29UFc"   "http://localhost:3000/protected"
```
## Success Flag Output
**{"message":"Access granted","user":{"email":"shivamofficialsm@gmail.com","sessionId":"ex7mqj","iat":1770932228,"exp":1770933128},"success_flag":"FLAG-c2hpdmFtb2ZmaWNpYWxzbUBnbWFpbC5jb21fQ09NUExFVEVEX0FTU0lHTk1FTlQ="}**
