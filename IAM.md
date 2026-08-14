IAM stands for Identity and Access Management. It is an AWS service used to control authentication and authorization to AWS resources. It allows us to ***manage users, groups, roles, and policies*** and define what actions an identity is allowed or denied to perform on AWS resources. For example, we can give an EC2 instance an IAM role that allows it to read objects from a specific S3 bucket without storing access keys on the server.



simply:

Who are you, and what are you allowed to do?





**# Main IAM Components:**



IAM

├── Users 		: Represents an individual identity that needs long-term AWS access.

├── Groups		: A collection of IAM users to which permissions can be assigned collectively.

├── Roles		: An IAM role is an identity with permissions that can be assumed by trusted entities such as AWS services, users, or applications.

└── Policies	: A JSON document that defines what actions are allowed or denied on AWS resources.

