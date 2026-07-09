# Terraform Layout

Suggested structure:

- `modules/` for reusable components
- `envs/dev/` for the first environment
- `envs/stage/` for later expansion

Start small:

- one access module
- one secure bucket module
- one security group module
- one EC2/EBS module
- one CloudWatch module

