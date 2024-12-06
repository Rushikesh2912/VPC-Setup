# Steps to Create a Custom VPC

When you create a VPC, AWS automatically creates a route table and a security group. The default route table is the main route table, which is used by private subnets.

## Steps to Create a Custom VPC

1. **Create a VPC.**
2. **Create Public and Private Subnets** in different Availability Zones.
3. **Create Route Tables** for both public and private subnets (if not already created).
4. **Create an Internet Gateway** and attach it to the VPC.
5. **Allocate an Elastic IP** if needed.
6. **Create a NAT Gateway** in the public subnet.
7. **Set Private Route Table** as the main subnet (no need for extra route tables for more private subnets).
8. **Associate Public Route Table** to the public subnet.
   - Select public route table → Edit subnet associations → Select public subnet → Save.
9. **Add Routes to Route Tables:**
   - Public Route Table: Target → Internet Gateway.
   - Private Route Table: Target → NAT Gateway.
   - Save routes.
10. **Modify Auto-Assign IP Settings** for public subnet:
    - Select public subnet → Modify auto-assign IP → Enable → Save.
11. **Enable DNS Hostnames** for the VPC:
    - Select VPC → Enable DNS hostnames → Enable → Save.
12. **Edit Security Group Rules** as required.
13. **Test the VPC** by launching instances in the subnets and testing internet connectivity.

### Deleting a VPC
To delete a VPC and its components:
1. Stop running instances using the VPC.
2. Delete the NAT Gateway.
3. Delete the VPC.
4. Release the Elastic IP.

### Notes
- For additional subnets, create them within the VPC. The main route table will automatically be used.

### Author : Rushikesh Shinde
### Contact : +91 9623548002
