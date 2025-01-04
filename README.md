# **How to Delete a Service in Windows Using CMD (sc delete)**

This guide explains how to stop and completely remove a service in Windows using the Command Prompt (CMD). You may need this process to optimize system performance, remove unnecessary services, or clean up malicious ones.

---

## **Why Would You Want to Delete a Service?**

1. **To Remove Unnecessary Services**: You might want to clean up leftover services after uninstalling a program you no longer need.  
2. **Performance Optimization**: Unused services can consume system resources.  
3. **Faulty or Malicious Services**: You may need to remove problematic or harmful services added by malware.  
4. **For a Fresh Start**: To fully reset and reinstall a misconfigured service.

---

## **Step-by-Step Guide to Deleting a Service**

### **1. Find the Service Name**

The easiest way to find the service name is through the Services application:

#### **Using the Services Application (services.msc):**

1. **Press `Win + R`:**  
   - This opens the Run dialog.  

2. **Type `services.msc` and Press Enter:**  
   - The Windows Services window will open.  

3. **Locate the Service You Want to Delete:**  
   - Find the service in the list, double-click it, and note the **Service Name** (not the display name).  
   - The Service Name will be used in the CMD commands.

---

### **2. Stop the Service**

Before deleting a service, it must be stopped if it is currently running. Follow these steps:

1. Open CMD as **Administrator**:  
   - Type **cmd** in the Start menu, right-click on Command Prompt, and select **Run as Administrator**.  

2. Use the following command to stop the service:  
   ```cmd
   sc stop service_name
   ```  
   **Example:** To stop a service named `MyTestService`, use:  
   ```cmd
   sc stop MyTestService
   ```  

   If the service is not running, this command will not throw an error, and you can proceed to the next step.

---

### **3. Delete the Service**

To permanently remove the service from the system, use the following command:  

```cmd
sc delete service_name
```  
**Example:** To delete a service named `MyTestService`, use:  
```cmd
sc delete MyTestService
```  

Once the command runs successfully, the service will be permanently removed from the system.

---

### **4. Verify the Service Is Deleted**

To ensure the service is no longer present, you can check the service list using this command:  

```cmd
sc query
```  

If the service no longer appears in the list, it has been successfully deleted.

---

## **Important Notes**

- **Administrator Privileges Required:** You must run CMD as an administrator for these commands to work.  
- **Use the Correct Service Name:** Make sure you enter the exact Service Name, not the Display Name. Double-check to avoid deleting the wrong service.  
- **Do Not Delete System-Critical Services:** Removing essential Windows services may cause system instability or crashes. If unsure, research the service before proceeding.  

---

With this guide, you now know how to stop and delete services in Windows safely. Be cautious during the process, and only modify services you are confident about!
