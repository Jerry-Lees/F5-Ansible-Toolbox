# F5-Ansible-Toolbox
# Step-by-Step upgrade notes for use
These files are meant as a proof of concept to get you started upgrading with ansible. They are functional, but are intended only for testing purposes. It is NOT recommended to use them in a production environment as is.
1. Install ansible and copy the ansible user's public key to the BIGIPs via ssh-copy-id
A good article on this process is here https://www.logicweb.com/knowledgebase/linux/how-to-setup-passwordless-ssh-login-in-linux-with-keys/
2. Install the daily build of the F5 ansible modules
The repository is located on github as well and has instructions in the readme.md https://github.com/F5Networks/f5-ansible
3. Populate the inventory/hosts file with your BIG-IPs in groupings of hosts. In the example they are names wave1 and wave2.
4. The images folder should contain any iso images to deploy to the BIG-IPs

You can run the playbooks in order, starting with:

ansible-playbook -i inventory/hosts playbooks/Step-by-Step_upgrade/1-copy_image.yml

Note that, a lot is hard coded that wouldn't normally be; like usernames/passwords, boot locations, and paths. These will need to be updated for you environment and it should be noted that this is not a good practice. Again, these are a proof of concept intended to provide guidance on what can be done with failrly simple ansible. More advanced ansible is left as an excercise for the reader.
