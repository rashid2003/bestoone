For install virtualenv <br>

###      sudo apt install virtualenv<br>
###      virtualenv .vts<br>
###     source .vts/bin/activate<br>


EROR :<br>
git@github.com: Permission denied (publickey).<br>
fatal: Could not read from remote repository.<br>
ADD NEW Generating a new SSH key For Fix that :<br>
1 -Open Terminal.<br>
2-Paste the text below, substituting in your GitHub email address.<br>
      ssh-keygen -t rsa -b 4096 -C "your_email@example.com"<br>
      This creates a new ssh key, using the provided email as a label.<br>
      Generating public/private rsa key pair.<br>
3-When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.<br>
      Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]<br>
4-At the prompt, type a secure passphrase. For more information, see "Working with SSH key passphrases". <br>
      Enter passphrase (empty for no passphrase): [Type a passphrase]<br>
      Enter same passphrase again: [Type passphrase again]<br>
      
# Adding your SSH key to the ssh-agent<br>
Before adding a new SSH key to the ssh-agent to manage your keys, you should have checked for <a href="https://help.github.com/articles/checking-for-existing-ssh-keys/">existing SSH keys</a> and <a href="https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#generating-a-new-ssh-key"> generated a new SSH key</a>. <br>
1-Start the ssh-agent in the background.<br>
     eval "$(ssh-agent -s)"<br>
      Agent pid 59566<br>
2-Add your SSH private key to the ssh-agent. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_rsa in the command with the name of your private key file.<br>
      ssh-add ~/.ssh/id_rsa<br>
