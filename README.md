#### Summary:

There are often times when you will need to investigate a website that you would rather not browse to using your local system, this CloudFormation stack aims to provide a relatively quick and painless to deploy solution that can be brought up and taken down as needed. I recommend that the EC2 instances are recycled regularly.

At launch Chromium, VNC and a desktop environment will be installed and configured such that once an SSH connection is established to the instance you can investigate your website using VNC over SSH without further authentication.

#### Deployment:

1. Deploy CloudFormation stack
2. Done

#### Usage:

0. Download and install a VNC client such as TigerVNC
1. Establish an SSH connection and port forward `ssh -fNT ec2-user@<EC2 PUBLIC IP FROM CLOUDFORMATION OUTPUT> -L 5901:127.0.0.1:5901`
2. On you local machine use your VNC client to connect to `127.0.0.1:5901`
3. Done

#### Future plans:

1. Better browser sandboxing i.e. Bubblewrap
2. Add some pre-installed analysis tools (potential move from AL2 to a more forensic focused distro)
3. Add ability to connect via an SSM tunnel rather than SSH to remove the burden of managing SSH keys
