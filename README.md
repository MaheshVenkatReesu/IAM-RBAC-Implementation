# IAM & RBAC Implementation in AWS

## 📌 Project Overview  
This project demonstrates how to implement IAM Policies & Role-Based Access Control (RBAC) in AWS, ensuring least privilege access, security best practices, and automation. It showcases the process of defining roles, creating custom policies, and enforcing MFA and logging for enhanced security.

## 🔹 Key Features  
✅ Role-Based Access Control (RBAC): IAM roles for Admins, Developers, and Auditors with permissions tailored for each group.  
✅ Custom IAM Policies: Fine-grained JSON-based policies for controlling access to AWS services and resources.  
✅ Multi-Factor Authentication (MFA): Enforced for privileged roles to add an additional layer of security.  
✅ Logging & Monitoring: AWS CloudTrail enabled to monitor and log user activities.  
✅ Automation (Optional): Terraform scripts to automate IAM role and policy creation.

## 📂 Project Structure  
- iam_policies/ → Contains JSON files for custom IAM policies.  
- terraform_scripts/ → Contains Terraform scripts for automating IAM setup (optional).  
- architecture_diagram.png → Visual representation of the RBAC model and access control flow.  
- security_audit_report.md → Document detailing the IAM security audit, findings, and recommendations.

## 📸 Architecture Diagram  
![IAM RBAC Architecture](architecture_diagram.png)  

## 🛠️ Implementation Steps  
1️⃣ Create IAM roles & policies:  
   - Use AWS IAM console or Terraform to define roles for Admins, Developers, and Auditors.  
   - Attach specific IAM policies based on the principle of least privilege.

2️⃣ Enforce MFA & CloudTrail logging:  
   - Enforce MFA for all privileged accounts to enhance security.  
   - Enable AWS CloudTrail for auditing and logging all user actions.

3️⃣ Define Custom Policies:  
   - Create fine-grained IAM policies that restrict permissions based on the user’s role.  
   - Use policy variables to dynamically assign permissions.

4️⃣ Conduct IAM Security Audit:  
   - Use IAM tools like IAM Access Analyzer and AWS Config to assess security posture.  
   - Document findings in the security_audit_report.md and suggest improvements.

## 🚀 Automation (Optional)  
- Terraform scripts can be used to automate IAM role and policy creation, ensuring consistency and scalability.

### Terraform Script Example:
```terraform
resource "aws_iam_role" "developer_role" {
  name               = "developer_role"
  assume_role_policy = data.aws_iam_policy_document.assume_role_policy.json
}

resource "aws_iam_policy" "developer_policy" {
  name        = "developer_policy"
  description = "Custom IAM policy for developer role"
  policy      = data.aws_iam_policy_document.developer_policy.json
}



🛡️ Security Best Practices
Least Privilege: Always assign the minimum necessary permissions for each role.
Enable MFA: Enforce MFA on all privileged accounts to reduce the risk of unauthorized access.
Access Logging: Use AWS CloudTrail for auditing and to keep track of API calls made by IAM users.
Periodic Review: Regularly review IAM roles, policies, and permissions to ensure they align with current security requirements.
📜 License
This project is open-source under the MIT License.
Feel free to use, modify, and distribute it as needed.

🔗 Related Links
AWS IAM Documentation
Terraform AWS Provider Documentation
