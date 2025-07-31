# ASG in AWS

## Let's first create a Image(ami)

### created app

### start ec2

### ssh into it, install node, clone the code, install dependencies, install bun, install pm2

#### test code

```bash
pm2 start --interpreter /home/ubuntu/.nvm/versions/node/v22.17.1/bin/bun bin.ts
#or
pm2 start --interpreter bun bin.ts
```

#### everything works? if yes then make a image from this container (go into aws, select container, then in actions you can make a image out of it)

### create launch template in aws.. (use the image we just made)

### add user data there, in advance options at bottom (this will run when the image starts)

```bash
#!/bin/bash
cd /home/ubuntu/Autoscaling-groups/
export PATH=$PATH:/home/ubuntu/.nvm/versions/node/v22.17.1/bin/bun
pm2 start --interpreter bun /home/ubuntu/bin.ts
```

#### now create launch template.

## Now Create a Target Group.

## Now Create a AutoScaling Group.. (in that you may create a Loadbalancer and attach your Target Group to it).

##### everything will work fine if you don't do any mistake.
