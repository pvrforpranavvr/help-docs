# 📊 JMeter Basics
## 🏗️ JMeter Test Plan Structure

A **Test Plan** is the top-level container for your performance test.

### 🧩 Basic Elements

- **Thread Group**  
  Defines the number of users (threads), ramp-up time, and loop count.

- **Samplers**  
  Simulate requests like:
  - HTTP Request
  - JDBC Request
  - FTP Request
  - SOAP/REST API calls

- **Listeners**  
  Display test results and statistics. Examples include:
  - View Results Tree
  - Summary Report
  - Aggregate Report

- **Assertions**  
  Validate responses (e.g., ensure `Response Code = 200` or response contains expected text).

- **Timers**  
  Add delays between requests to simulate real-world usage.

- **Pre/Post Processors**  
  Manipulate requests or responses:
  - Pre-Processors (run before a sampler)
  - Post-Processors (run after a sampler)

- **Config Elements**  
  Set default values or shared settings across samplers, such as:
  - HTTP Request Defaults
  - HTTP Header Manager
  - CSV Data Set Config (for data-driven testing)
    


