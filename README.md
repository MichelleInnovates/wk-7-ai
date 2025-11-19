# wk-7-ai
🌍⚖️ Designing Responsible and Fair AI Systems: AI Ethics Audit

This repository contains the full submission for the AI Ethics Assignment, focusing on the principles, practical application, and policy implications of designing trustworthy AI systems, adhering to guidelines like the EU Ethics Guidelines for Trustworthy AI.

🎯 Assignment Objectives

The primary goal of this project was to evaluate our ability to identify, analyze, and mitigate algorithmic bias across both theoretical and practical scenarios. The assignment was structured into four core parts:

Theoretical Understanding: Defining key ethical concepts (bias, transparency, explainability).

Case Study Analysis: Analyzing real-world scenarios (Biased Hiring Tool, Facial Recognition in Policing).

Practical Audit: Using the AI Fairness 360 toolkit to audit a real-world dataset (COMPAS).

Ethical Reflection: Applying principles to a personal project.

Bonus Task: Drafting a focused policy proposal for AI in healthcare.

📦 Project Deliverables & File Structure

This submission consists of four primary files, covering all parts of the assignment:

File Name

Description

Corresponds to

ai_ethics_report.md

Contains all written, non-code answers: Part 1 (Theory), Part 2 (Case Studies), and Part 4 (Reflection).

Written Submission

bias_audit.py

The Python script that downloads the COMPAS dataset, performs pre-processing, calculates fairness metrics (DI, Mean Difference), and generates a visualization.

Part 3 Code

audit_summary.md

A concise, 300-word report summarizing the findings and proposed remediation strategy from the bias_audit.py script.

Part 3 Report

healthcare_ai_policy.md

The Bonus Task policy proposal covering patient consent, bias mitigation, and transparency in healthcare AI use.

Bonus Task

fairness_audit_chart.png

Generated Output: A visualization showing the comparison of actual vs. ideal fairness metrics (Disparate Impact and Mean Difference).

Part 3 Output

🛠️ Technical Setup and Execution (Part 3)

The practical audit relies on Python and the IBM AI Fairness 360 toolkit (aif360).

Prerequisites

You must have Python 3.x installed.

1. Installation

Install all required dependencies using pip:

pip install aif360 pandas matplotlib numpy requests


2. Running the Audit

The bias_audit.py script is designed to be self-contained. It handles downloading the necessary raw COMPAS data directly from the ProPublica repository, cleans it, and executes the audit.

Run the script from your terminal:

python bias_audit.py


Script Output

Running the script will produce two main results:

Console Output: Prints the calculated Disparate Impact Ratio and Mean Difference, along with a draft of the audit summary report.

File Output: Generates the fairness_audit_chart.png file, visualizing the results.

📊 Key Findings from the Practical Audit

The audit of the COMPAS dataset focused on racial bias where African-Americans were the unprivileged group and Caucasians were the privileged group, with the favorable outcome being "No Recidivism."

Metric

Result (Typical)

Interpretation

Disparate Impact Ratio (DI)

~0.60

Fails the 0.80 threshold. African-Americans are significantly less likely to be classified as low risk.

Mean Difference

~-0.20

Confirms statistical disparity, showing Caucasians receive the favorable outcome at a higher rate.

Proposed Remediation:

To address the bias present in the data, the report recommends using a Pre-processing Intervention such as the Reweighing Algorithm. This technique adjusts instance weights in the training data to enforce Statistical Parity across the protected groups before model training begins, aiming to achieve a DI closer to 1.0.

📚 Ethical Frameworks Applied

The analysis and policy work within this project were guided by:

EU Ethics Guidelines for Trustworthy AI: Focus on fairness, transparency, and accountability.

AIF360 Metrics: Specific use of Disparate Impact and Mean Difference to quantify bias.