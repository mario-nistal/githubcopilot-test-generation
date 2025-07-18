# Example 1:

### **API Details:**  
- **Endpoint:** `https://127.0.0.1/gateway/api/v1/login-user`  
- **Supported Methods:** `Get`
- **Request Body Schema:**  
  ```json
  {
    "username": "xxxx",
    "password": "xxxxxxxx"
  }
  ```  
  - **username is required.**
  - **password is required.**  

- **Expected Response Schema:**  
  ```json
  {
    "access_token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
  }
  ``


# Example 2:
create test cases for the workitem 1306802 based on its acceptance criteria