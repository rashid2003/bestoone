sudo apt install virtualenv
virtualenv .vts
source .vts/bin/activate


EROR :
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.
ADD NEW Generating a new SSH key For Fix that :
1 -Open Terminal.
2-Paste the text below, substituting in your GitHub email address.
      ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
      This creates a new ssh key, using the provided email as a label.
      Generating public/private rsa key pair.
3-When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.
      Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]
4-At the prompt, type a secure passphrase. For more information, see "Working with SSH key passphrases". 
      Enter passphrase (empty for no passphrase): [Type a passphrase]
      Enter same passphrase again: [Type passphrase again]
      
# Adding your SSH key to the ssh-agent
Before adding a new SSH key to the ssh-agent to manage your keys, you should have checked for <a href="https://help.github.com/articles/checking-for-existing-ssh-keys/">existing SSH keys</a> and <a href="https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#generating-a-new-ssh-key"> generated a new SSH key</a>. 
1-Start the ssh-agent in the background.
     eval "$(ssh-agent -s)"
      Agent pid 59566
2-Add your SSH private key to the ssh-agent. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_rsa in the command with the name of your private key file.
      ssh-add ~/.ssh/id_rsa
