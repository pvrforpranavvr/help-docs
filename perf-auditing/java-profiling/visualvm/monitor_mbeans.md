# 📘 MBeans Plugin in VisualVM

The **MBeans Plugin** in **VisualVM** provides an interface to monitor and manage **JMX MBeans** (Managed Beans) registered in a Java application. MBeans are part of the Java Management Extensions (JMX) framework and allow real-time monitoring and management of application internals.

---

## 🔍 What Is It Used For?

The MBeans plugin enables you to:

- Browse all MBeans registered in a JVM
- View and monitor MBean **attributes** (e.g., memory, threads, custom metrics)
- **Invoke operations** defined in MBeans (e.g., reset stats, trigger GC)
- Listen for **notifications** sent by MBeans
- Plot **live charts** of numeric attributes over time

Useful for:

- Monitoring custom application metrics
- Debugging and performance tuning
- Managing enterprise applications (e.g., via JMX in Spring Boot or Tomcat)
- Check hikari connection pools

---

## ⚙️ How to Set Up

### 1. Install the MBeans Plugin in VisualVM

1. Open **VisualVM**
2. Navigate to `Tools` → `Plugins`
3. Under `Available Plugins`, check **MBeans**
4. Click `Install` and follow the wizard
5. Restart VisualVM if prompted

---

### 2. Enable JMX in Your Java Application

#### Option A: Local Application

- No configuration needed. VisualVM detects and attaches to local processes automatically.

#### Option B: Remote or Custom Configuration

Add these JVM options to your application:

```bash
-Dcom.sun.management.jmxremote
-Dcom.sun.management.jmxremote.port=9010
-Dcom.sun.management.jmxremote.ssl=false
-Dcom.sun.management.jmxremote.authenticate=false
```
