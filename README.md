<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# AI Security Scanner for Python

**Project Link:** [View Project](http://learn.nextwork.org/projects/ai-security-audit)

**Author:** Rahul Allamraju  
**Date:** 

---

![Image](http://learn.nextwork.org/mischievous_azure_silly_grape/uploads/ai-security-audit_sec4e5f6)

---

## Introducing Today's Project!

In this project, I'm going to build an AI security scanner using Gemini API. This will help me learn about SQL injections and other vulnerabilities. 

### Key tools and concepts

Tools I used were Gemini API and Python libraries. Key concepts I learnt include making structured prompts so that the AI gives accurate answers. The most important skill was the security prompt which tells the AI exactly what to do and this can be tailored to the user's need. 

### Challenges and wins

This project took me approximately 2 hours. The most challenging part was understanding the different types of vulnerabilities. It was most rewarding to see Gemini give suggestions on how to fix the vulnerabilities. 

### Why I did this project

I did this project today because I'm very interested in cybersecurity. This project met my goals by using AI for security purposes. Next, I plan to try to apply this to bigger projects and expand this scanner into something more user friendly

---

## Connecting to Gemini API

In this step, I'm setting up the Gemini API connection. This involves setting up an .env file witht he API key. I need to do this so I can test the connection to Gemini.

![Image](http://learn.nextwork.org/mischievous_azure_silly_grape/uploads/ai-security-audit_sec2c3d4)

I verified the connection by running my scanner.py file that sets up a connection to Gemini and sends a test message to verify it's working. Gemini responded with a greeting message which confirmed that the connection is working.

![Image](http://learn.nextwork.org/mischievous_azure_silly_grape/uploads/ai-security-audit_sec4e5f6)

My scanner.py file works by sending the code to the Gemini API and asks AI to analyze the code. When I ran it, Gemini identified that having the hardcoded password is a security issue. This shows that the Gemini API can understand the code and catch vulnerabilities in code. 

---

## Building the Vulnerability Scanner

In this step, I'm building a vulnerability scanner that can detect SQL injection, hardcoded secrets, and weak cryptography.

![Image](http://learn.nextwork.org/mischievous_azure_silly_grape/uploads/ai-security-audit_sec7h8i9)

The vulnerabilities Gemini detected were the username parameter wasn't parameterized, the password was embedded into the source code, and the weak password hashing algorithm. The security prompt I crafted asked for  alternative security measures. This structured output helps me structure the code in a safer way to protect information.

---

## Adding Severity Ratings

In this step, I'm adding severity ratings which will clearly show the level of risk. I'm also installing colorama to color code the vulnerabilities.

![Image](http://learn.nextwork.org/mischievous_azure_silly_grape/uploads/ai-security-audit_sec0k1l2)

I updated the security prompt to include SEVERITY: [CRITICAL/HIGH/MEDIUM/LOW]
The add_colors_to_output function takes text as input, adds color codes to severity levels, and returns the colorized text. When I see CRITICAL in red, it tells me that the system can be compromised and this must be fixed immediately. 

---

## Scanning Real Python Files

In this secret mission, I'm adding file reading capability to the scanner. This lets the scanner create vulnerable test file to scan. Professional tools do this because they can scan real files in production codebases like security teams do.

![Image](http://learn.nextwork.org/mischievous_azure_silly_grape/uploads/ai-security-audit_sec3n4o5)

I scanned vulnerable.py by running it through the scanner.py file. The vulnerabilities detected were SQL Injection, Hardcoded Credentials, Hashing algorithm, and command injection. The scan_file function works by reading a Python file from your computer, sends its contents to Gemini for security analysis, and prints the colored results. 

---

## Wrap-up

---

---
