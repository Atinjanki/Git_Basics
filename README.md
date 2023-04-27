# Test File

This is for testing purposes!

## Subheader

Subheader text!

## Git Status
Before comminting do-
    git status

## Git Add
Then you would find list of modified and untracked (newly added) files.
To let git know about these modifications/additions, do-

    git add .

here instead of '.' , you could also write the name of the file or folder!

## Git Commit
Once you have done that, then commit the code (locally) on your machine! Do-

    git commit -m "Message title for commit" -m "Message description for commit"

Now the commit has been done locally and our remote repository(where project is hosted) which could be on Github, Gitlab etc, still needs this updation (push)!

## SSH connection
So to do 'git push', we need SSH key to connect to our code to remote repository to push our code from local machine.
Do (follow instructions from https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)-

    ssh-keygen -t ed25519 -C "your_email@example.com"

This creates a new SSH key, using the provided email as a label.
And generates public/private ALGORITHM key pair!

When you're prompted to "Enter a file in which to save the key", you can press Enter to accept the default file location. Please note that if you created SSH keys previously, ssh-keygen may ask you to rewrite another key, in which case we recommend creating a custom-named SSH key. To do so, type the default file location and replace id_ssh_keyname with your custom key name.

    > Enter a file in which to save the key (/c/Users/YOU/.ssh/id_ALGORITHM):[Press enter]
At the prompt, type a secure passphrase. For more information, see "Working with SSH key passphrases."

    > Enter passphrase (empty for no passphrase): [Type a passphrase]
    > Enter same passphrase again: [Type passphrase again]

Also, add your SSH key to the ssh-agent
Before adding a new SSH key to the ssh-agent to manage your keys, you should have checked for existing SSH keys and generated a new SSH key.

If you have GitHub Desktop installed, you can use it to clone repositories and not deal with SSH keys.

Ensure the ssh-agent is running. You can use the "Auto-launching the ssh-agent" instructions in "Working with SSH key passphrases", or start it manually:

# start the ssh-agent in the background
    $ eval "$(ssh-agent -s)"
    > Agent pid 59566
Add your SSH private key to the ssh-agent. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_ed25519 in the command with the name of your private key file.

    $ ssh-add ~/.ssh/id_ed25519
Add the SSH key to your account on GitHub. For more information, see "Adding a new SSH key to your GitHub account."

To auto-launch SSH-Agent every time Git bash loads, follow this -https://docs.github.com/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases?platform=windows.

If the 'agent.env' file does not exist, then start 'ssh-agent' manually and do-
    ssh-agent > ~/.ssh/agent.env

Then upload this key (public one as the private key should stay on local machine) to Github by going to Settings--> SSH keys--> Add new SSh Key (by copying the contents of the key file).

## git push
git push origin main
