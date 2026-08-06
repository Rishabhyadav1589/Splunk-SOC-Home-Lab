# Splunk Universal Forwarder Installation

## Objective

Install and configure the Splunk Universal Forwarder on the Windows endpoint to securely forward Windows Event Logs and Sysmon logs to Splunk Enterprise.

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Endpoint | Windows 10 VM |
| Log Forwarder | Splunk Universal Forwarder |
| Destination | Splunk Enterprise |
| Port | 9997 |

---

# Download Universal Forwarder

Download the Windows version of Splunk Universal Forwarder from the official Splunk website.

---

# Installation Steps

## Step 1

Run the installer as Administrator.

---

## Step 2

Accept the License Agreement.

---

## Step 3

Choose:

```
Local System
```

---

## Step 4

Enter Splunk Server Details.

```
Receiving Indexer

IP Address : <Splunk Server IP>

Port : 9997
```

---

## Step 5

Finish the installation.

---

# Verify Forwarder Service

Open Command Prompt.

```
sc query splunkforwarder
```

Expected Result:

```
STATE : RUNNING
```

---

# Verify Connection

On Splunk Server

```
sudo /opt/splunk/bin/splunk list forward-server
```

Expected Output

```
Active forwards:

<Windows-IP>:9997
```

---

# Screenshots

Add screenshots here.

- Universal Forwarder Installation
- Receiving Indexer Configuration
- Splunk Connected Forwarder

---

# Outcome

The Windows endpoint is successfully connected to Splunk Enterprise and is ready to forward Windows Event Logs and Sysmon logs.
