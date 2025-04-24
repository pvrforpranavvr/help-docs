## 🚀 Creating a Simple HTTP Test

Follow these steps to create a basic test plan in JMeter:

---

### 1️⃣ Add a Thread Group

- **Users (Threads)**: `10`  
- **Ramp-up Period (seconds)**: `5`  
- **Loop Count**: `1`

Right-click on **Test Plan** > `Add` > `Threads (Users)` > `Thread Group`

---

### 2️⃣ Add a HTTP Request Sampler

- **Server Name or IP**: `example.com`  
- **Path**: `/api/test`  
- **Method**: `GET`

Right-click on **Thread Group** > `Add` > `Sampler` > `HTTP Request`

---

### 3️⃣ Add a PreProcessor (Optional)

Use a **User Defined Variables** config element if you want to set variables dynamically before requests.

- Right-click on **HTTP Request** > `Add` > `Pre Processors` > `User Parameters` or `JSR223 PreProcessor`
- Example:
  ```groovy
  vars.put("userId", "12345");
  ### 4️⃣ Add a PostProcessor to Extract a JSON Value

Use the **JSON Extractor** to extract fields from the JSON response.

📍 **Steps:**

- Right-click on **HTTP Request** > `Add` > `Post Processors` > `JSON Extractor`

🛠 **Configuration:**

- **Name of created variable**: `token`  
- **JSON Path Expressions**: `$.data.token`

💡 You can now reference the extracted value in subsequent requests using `${token}`.

---

### 5️⃣ Add Listeners to View Results

Add one or more listeners to visualize your test results.

📍 **Options:**

- **View Results Tree**
- **Summary Report**
- **Aggregate Report**

📂 **How to Add:**

Right-click on **Thread Group** > `Add` > `Listener` > Select any of the above

---
