
This project, entails onboarding 20 new Linux users onto a server. Used the shell script in the  https://github.com/darey-devops/Auxilarry-project-1   repository that reads a csv file that contains the first name of the users to be onboarded.

spun up an ubuntu server named Aux-project
![1  create a auox project instance](https://user-images.githubusercontent.com/79456052/181995888-bdb85f4a-2394-468c-964d-0af93a6562a9.png)

created a file called onboard.sh and copied the shell script in the https://github.com/darey-devops/Auxilarry-project-1 into the onboard.sh file

![3  shell script for the onboard users](https://user-images.githubusercontent.com/79456052/181996264-388e19e4-f99b-4e83-8296-f15fdf629f7a.png)

Created the project folder called shell using the *mkdir shell* command and copied the onboard.sh file into the /home/ubunty/shell directory using the command *mv onboard.sh /home/ubuntu/shell* directory.
Created the id_rsa, id_rsa.pub and names.csv files using the command *touch id_rsa id_rsa.pub names.csv*

![2a  the commands used before ](https://user-images.githubusercontent.com/79456052/181996115-d3dc1cdd-2a49-40e1-9729-6bb0d017609b.png)


Added the public keu from the documentation in the id_rsa.pub file. 
![4  create id_rsa pub](https://user-images.githubusercontent.com/79456052/181996440-b5128826-338d-45dc-9626-e24235091779.png)

Added the  private key in the documetnation in the id_rsa file 
![5  create id_rsa file](https://user-images.githubusercontent.com/79456052/181996505-f3d8e936-0b07-49a2-bdb5-f46df66e3ed4.png)

added the names of the 20 new Linux users needed to be onboarded in the names.csv file.
![6   vreate the names csv file](https://user-images.githubusercontent.com/79456052/181996538-708aeca1-2374-422a-8f9f-0753d6484284.png)

Changed the path of the id_rsa.pub in the onborad.sh  to /home/ubuntu/shell/id_rsa.pub so that it can be copied over to the /home/$user/.ssh/authorized_keys.

![7  Change the path of the id_rsa pub in the onborad sh file so that it can be copied over to the :home:$user: ssh:authorized_keys](https://user-images.githubusercontent.com/79456052/181996609-59e0d9bd-99aa-4d1c-a2b8-a995fa1dc5d7.png)

switched  user to root using the command *sudo su* and made onboard.sh an excutable file using the command *sudo chmod +x onboard.sh*

![8  su user to root and Make onboard sh an excutable file using the command sudo chmod +x onboard](https://user-images.githubusercontent.com/79456052/181996700-2fa21483-f37c-4091-be04-c27caf6e6ee7.png)


Ran the excutable file ./onboard.sh creating all the users in the names.csv file.
