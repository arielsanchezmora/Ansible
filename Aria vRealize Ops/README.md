I was trying to get this code to work

https://www.nicktailor.com/?p=1888

Turns out I had to change it quite a bit with the latest version of Ansible and vRealize/Aria/VCF Operations, but now I can login and save the authentication token, and use to call another API endpoint!

Latest code is here:

https://github.com/arielsanchezmora/Ansible/blob/main/Aria%20vRealize%20Ops/check_vrops_status.yml


Old issue:

Original code from the blog post with my environment credentials (don't worry, these only work in my lab):

![OriginalCode](https://github.com/arielsanchezmora/Ansible/blob/main/Aria%20vRealize%20Ops/original%20code.png)


I'm getting an error that it doesn't see any json in the output of the auth request, which can be seen as the debug before the error occurs. Actual error is "The task includes an option with an undefined variable. The error was: 'dict object' has no attribute 'json'. "

It seems that for some reason, I'm not being able to access the actual token in the json body, I'm only registering the headers.

![playbookRun](https://github.com/arielsanchezmora/Ansible/blob/main/Aria%20vRealize%20Ops/original%20ansible%20playbook.png)

When I try on the Swagger API interface the Ops instance brings, I can see the body and the headers in separate response sections. How do I access the token in the body inside the ansible playbook?

![APIswagger](https://github.com/arielsanchezmora/Ansible/blob/main/Aria%20vRealize%20Ops/ops%20swagger%20api%20interface%20showing%20body.png)
