# Microsoft Entra ID — Password Protection & Smart Lockout

Explore how **Microsoft Entra ID** helps protect user accounts by enforcing stronger passwords, blocking commonly used or organization-specific passwords, and restricting repeated login attempts to reduce the risk of password attacks.

> **Estimated completion time:** 5 minutes

---

## 🎯 Objectives

By completing this exercise, you will learn how to:

* Configure **Smart Lockout** settings.
* Define a custom **banned password list**.
* Enforce password protection policies.
* Configure account lockout thresholds and durations.
* Reduce the risk of password-based attacks.

---

## Prerequisites

Before you begin, make sure you have:

* Access to a Microsoft Entra tenant.
* Credentials with sufficient permissions to modify password protection settings.
* Access to the **Microsoft Entra admin center**.

---

# Task 1 — Configure Smart Lockout and Password Protection

In this task, you will review the existing password protection settings and configure custom Smart Lockout and banned password policies.

### Step 1 — Open Microsoft Entra admin center

Open the [Microsoft Entra admin center](https://entra.microsoft.com/) at:

`https://entra.microsoft.com`

Sign in using the credentials for your tenant.

---

### Step 2 — Navigate to Password Protection

From the left-hand navigation menu:

1. Select **Protection**.
2. Select **Authentication methods**.
3. Select **Password protection**.

> **💡 Tip:** You can also search for **Password protection** using the search bar at the top of the Microsoft Entra admin center.

---

### Step 3 — Configure Custom Smart Lockout

Locate the **Custom smart lockout** settings and configure the following values:

| Setting               |        Value | Description                                                                          |
| --------------------- | -----------: | ------------------------------------------------------------------------------------ |
| **Lockout threshold** |          `5` | Number of failed password attempts allowed before the account is temporarily locked. |
| **Lockout duration**  | `30` seconds | Amount of time the account remains locked after the threshold is reached.            |

> **Note:** You can also configure a custom banned password list from this page.

---

### Step 4 — Enable the Custom Banned Password List

Set:

**Enforce custom list** → **Yes**

Then add the following words to the custom banned password list:

```text
Contoso
London
Widget
```

### 💡 Lab Tip

The lab environment represents a company called **Contoso**, located in **London**, that manufactures **Widgets**.

Adding these terms to the banned password list prevents users from using these words, either individually or as part of a password.

---

### Step 5 — Enable Password Protection

Set:

**Mode** → **Enforced**

This ensures that the configured password protection policy is actively enforced rather than simply being evaluated.

---

### Step 6 — Save the Configuration

Select **Save** at the top of the page.

Your Microsoft Entra password protection configuration should now resemble the following:

| Configuration       | Value                       |
| ------------------- | --------------------------- |
| Lockout threshold   | **5 attempts**              |
| Lockout duration    | **30 seconds**              |
| Enforce custom list | **Yes**                     |
| Banned passwords    | **Contoso, London, Widget** |
| Mode                | **Enforced**                |

---

## ✅ Task Completion Checklist

* [ ] Opened the **Microsoft Entra admin center**
* [ ] Navigated to **Protection → Authentication methods → Password protection**
* [ ] Set the lockout threshold to **5**
* [ ] Set the lockout duration to **30 seconds**
* [ ] Enabled the custom banned password list
* [ ] Added `Contoso`
* [ ] Added `London`
* [ ] Added `Widget`
* [ ] Set the mode to **Enforced**
* [ ] Saved the configuration

---

## 🧠 Key Takeaways

Microsoft Entra ID provides multiple controls for defending against password-based attacks:

* **Smart Lockout** temporarily locks accounts after repeated failed sign-in attempts.
* **Custom banned passwords** prevent users from choosing organization-specific or easily guessable terms.
* **Enforced mode** ensures the password protection policy is actively applied.

Together, these controls help reduce the effectiveness of **password guessing, brute-force, and password-spraying attacks**.
