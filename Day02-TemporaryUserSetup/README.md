# Step 1: Connect to App Server 2
ssh steve@stapp02

# Step 2: Create user with expiry date
sudo useradd -e 2024-02-17 kareem

# Step 3: Set password
sudo passwd kareem

# Step 4: Verify expiry
sudo chage -l kareem

# Step 5: Exit
exit
