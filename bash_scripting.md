
This project, entails onboarding 20 new Linux users onto a server. Used the shell script in the  https://github.com/darey-devops/Auxilarry-project-1   repository that reads a csv file that contains the first name of the users to be onboarded.

spun up an ubuntu server named Aux-project
![1  create a auox project instance](https://user-images.githubusercontent.com/79456052/181995888-bdb85f4a-2394-468c-964d-0af93a6562a9.png)

created a file called onboard.sh and copied the shell script in the https://github.com/darey-devops/Auxilarry-project-1 into the onboard.sh file

![3  shell script for the onboard users](https://user-images.githubusercontent.com/79456052/181996264-388e19e4-f99b-4e83-8296-f15fdf629f7a.png)

Created the project folder called shell using the *mkdir shell* command and copied the onboard.sh file into the /home/ubunty/shell directory using the command *mv onboard.sh /home/ubuntu/shell* Created the id_rsa, id_rsa.pub and names.csv files using the command *touch id_rsa id_rsa.pub names.csv*

![2a  the commands used before ](https://user-images.githubusercontent.com/79456052/181996115-d3dc1cdd-2a49-40e1-9729-6bb0d017609b.png)


Added the public keu from the documentation in the id_rsa.pub file. 
![4  create id_rsa pub](https://user-images.githubusercontent.com/79456052/181996440-b5128826-338d-45dc-9626-e24235091779.png)

Added the  private key in the documetation in the id_rsa file 
![5  create id_rsa file](https://user-images.githubusercontent.com/79456052/181996505-f3d8e936-0b07-49a2-bdb5-f46df66e3ed4.png)

added the names of the 20 new Linux users needed to be onboarded in the names.csv file.
![6   vreate the names csv file](https://user-images.githubusercontent.com/79456052/181996538-708aeca1-2374-422a-8f9f-0753d6484284.png)

Changed the path of the id_rsa.pub in the onborad.sh  to /home/ubuntu/shell/id_rsa.pub so that it can be copied over to the /home/$user/.ssh/authorized_keys.

![7  Change the path of the id_rsa pub in the onborad sh file so that it can be copied over to the :home:$user: ssh:authorized_keys](https://user-images.githubusercontent.com/79456052/181996609-59e0d9bd-99aa-4d1c-a2b8-a995fa1dc5d7.png)

switched  user to root using the command *sudo su* and made onboard.sh an excutable file using the command *sudo chmod +x onboard.sh*

![8  su user to root and Make onboard sh an excutable file using the command sudo chmod +x onboard](https://user-images.githubusercontent.com/79456052/181996700-2fa21483-f37c-4091-be04-c27caf6e6ee7.png)

Ran the excutable file ./onboard.sh creating all the users in the names.csv file.

![9  all users in the CSV file are created](https://user-images.githubusercontent.com/79456052/181997302-8c5662af-4bd9-4d53-a528-56b7f7765ba5.png)

![10  confirm that the users have been created in the :home directory](https://user-images.githubusercontent.com/79456052/181997332-92293ce1-eeca-4b90-a104-e6153f0ffd8d.png)

Used the command *cat /etc/passwd | awk -F':' '{ print $1}' | xargs -n1 groups* to filter the names of the users in the developers group


![11  used a commant cat:etc   to folter the names of the users in the developers group](https://user-images.githubusercontent.com/79456052/181999465-b14dd508-9bd2-4dd7-9c78-a340b1e37e02.png)


![ 12  Confirm that the   developer group has been created](https://user-images.githubusercontent.com/79456052/181999876-27c5be26-da0e-4f91-80ab-c2ac0d85d173.png)

In Testing a few of the users randomly and ensuring connection to the server using the private key and the public key, I created a auxproj.pem private key file on my local machine, added the content of the private key in the documetation to the auxproj.pem file, changed the permissions on the auxproj.pem using the command *sudo chmod 600 auxproj.pem* to keep the private key protected. Sshed successfully into the server using the user David with the command *ssh -i auxproj.pem David@3.87.63.24

![13](https://user-images.githubusercontent.com/79456052/182002266-1c67f3af-b586-4289-9d5a-40ebf646e228.png)


![12b](https://user-images.githubusercontent.com/79456052/182001888-1e60fb26-cbde-4a8e-9e51-a374f133fcd5.png)

![12c](https://user-images.githubusercontent.com/79456052/182002101-41f6bc01-0e1d-4ee2-acb1-14bf9ce6afd0.png)


logged out and sshed successfully  into the server using another user James with the command *ssh -i auxproj.pem Jams@3.87.63.24* The screnshot below also shows that James and David are not sudoers i.e meaning they can't carryout priviledged commands using sudo e.g using  command like *sudo apt update*

![12d](https://user-images.githubusercontent.com/79456052/182002212-596f4298-1364-474c-ab97-25a14cd96c90.png)












