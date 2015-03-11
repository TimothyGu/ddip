# ddip

**Scripts are not checked into Git yet**

A very crude attempt in managing dynamic IPs.

Have you had a moment when you want to SSH to your RPi at home but don't know the IP? I do too!

This is not targeted at DDNS management. ddclient is your friend there.

## How to use

1. [Create a secret Gist](https://gist.github.com/).
2. [Create an SSH key](https://help.github.com/articles/generating-ssh-keys), either passphrase-less or you can try to get `ssh-agent` working. I'm not counting on the latter.
3. [Add that SSH key to your GitHub account](https://help.github.com/articles/generating-ssh-keys).
4. Clone this repo.
5. In the directory, create a file called `url` with the SSH URL of your Gist in it.
6. Run `./init.sh`.
7. Run `crontab -e` and add the follow line:

  ```crontab
  0 * * * * cd WHERE_YOU_PUT_THIS_REPO && ./script.sh
  ```

Now, the Gist will be updated every hour, and even if the IP didn't change a commit will still be pushed to show that the IP is current.

## License

MIT
