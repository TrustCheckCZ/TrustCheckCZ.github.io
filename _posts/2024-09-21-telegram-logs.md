---
layout: post  
title: "How log clouds are taking over Telegram"  
categories:  
- privacy  
- piccioni  
- logs  
- leaks  
author:  
- The Trust Check Team  
---

Lately, there's been a noticeable rise in the use of so-called "log clouds"—platforms that aggregate stolen data, including **device logins**, which contain sensitive information such as URLs, usernames, and passwords. These platforms are becoming increasingly popular within underground communities due to their accessibility and the sheer volume of data they provide.

## The Big Dogs

Several key players have emerged within these underground spaces, including but not limited to:

1. **Piccioni**
2. **TXT Cloud**
3. **Arkady**

These platforms often operate on **Telegram**, where they offer logs for sale or trade, catering to the needs of those involved in malicious cyber activities. Below, we'll dive deeper into one of these clouds: **Piccioni**.

---

## **1. TXT Cloud**

TXT Cloud is one of the most prominent **Telegram-based log clouds**, widely recognized for its community-driven pricing model. It markets itself as a blend of **public and private log access**, offering large volumes of stolen credentials at relatively low prices, making it a popular destination in the underground world.

#### **Cloud Description**
> "We have over 10 billion strings in our database and all of them are unique. At the start of the development of our cloud we will publish for you every day from 5 million to 20 million strings. More to come."

Source: https://t.me/urllogpas

As of writing this post, there have been `229` total files posted in said cloud.

## **2. Piccioni**

Piccioni is new to the game in **Telegram-based log clouds**, but is making a significant impact by offering both **public and private log access**, with huge volumes of stolen credentials for **free**.

#### **Cloud Description**
Piccioni promotes itself as follows:
> "Piccioni is a public and private log cloud with reasonable and cheap pricing based on the community’s desires."

Operated by `@piero_piccioni` on Telegram, this cloud has amassed a significant following, thanks to its vast selection of logs, ease of access, and competitive pricing. The cloud is used by both newcomers and seasoned individuals in the data-leaking community.

As of writing this post, there have been `522` total files posted in said cloud.

---

### Data Analysis on Clouds

Following a small analysis of this cloud in a single file, we found `49,859` unique, never-before-seen leaked email and password combinations.  
From just 7 files out of **hundreds**, there were *9,413,874* leaked users and over *428,902* never-before-seen leaked email addresses.

### 1. Unique Emails and Passwords
Out of the total dataset analyzed, we discovered:
- **428,902 unique email:password combinations**.
- This suggests a significant portion of new data breaches, contributing to the overall landscape of exposed credentials.

### 2. Volume of Data
- The **7 files** examined contain **9,413,874 leaked users**—a staggering number of compromised individuals.
- The **317 MiB** of newly leaked data represents not just emails but also sensitive password information that could have far-reaching consequences if abused.
  
### 3. Domains and Password Patterns
Further analysis showed:
- **Top email domains**: The majority of the leaked emails were from well-known domains such as `gmail.com`, `yahoo.com`, and `hotmail.com`.
- **Common passwords**: Weak passwords, including `123456`, `password`, and `qwerty`, continue to be prevalent, highlighting the ongoing issue of poor password practices.
![Figure2](/assets/images/password_graphs/Figure_2.png)

### 4. Password Length and Complexity
- **Password length distribution**: The majority of leaked passwords are between 6-10 characters long, indicating that users still favor shorter, less secure passwords.
- **Complexity**: Less than **8%** of the passwords analyzed contained special characters or a mix of uppercase and lowercase letters, suggesting a lack of password complexity in the majority of the dataset.
![Figure1](/assets/images/password_graphs/Figure_1.png)
![Figure3](/assets/images/password_graphs/Figure_3.png)

### 5. Impact of the Leak
Given the large number of new, never-before-seen combinations, this leak represents a significant addition to the pool of compromised credentials.  
The presence of weak passwords and popular email domains means that this data is highly exploitable, posing risks for credential stuffing attacks, identity theft, and more.

## Dataset Analysis
To facilitate the analysis of the leaked data, we developed a lightweight Python utility that scans the dataset and visualizes key distributions such as password complexity and domain patterns. You can find the tool on GitHub:  
[log-analysis utility](https://github.com/JStuborn/log-analysis/tree/main)

### Usage Instructions:
1. Move all data files to the `./data` directory.
2. Run the script with the following command:
   ```bash
   python main.py
    ```
This utility automates the analysis process, making it easier to gain insights into the leaked data without manual intervention.

## Conclusion

The rise of log clouds like Piccioni and TXT Cloud illustrates the growing threat posed by the illicit exchange of stolen data in underground communities. These platforms, especially on Telegram, provide malicious actors with easy access to vast amounts of credentials, leaving both individuals and organizations at risk. The analysis of the data from these platforms reveals worrying trends, such as the use of weak passwords and the exposure of sensitive information.

To mitigate the risks associated with such leaks, users must adopt stronger password practices, including the use of password managers and two-factor authentication (2FA). Organizations should also remain vigilant, constantly updating their security measures to guard against the exploitation of compromised credentials.
