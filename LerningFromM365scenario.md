# Business Requirements
* Need to ensure that user’s identities are as secure as possible with minimal overhead to user’s day to day operations – for example username / password prompts should be kept to a minimum – if at all
*	There are several internal apps that are used that require VPN, Contoso wants to do away with VPN for various reasons but still need to grant users who are mobile access to these internal apps
 
# Technical Requirements
*	Solution should either leverage existing ADFS infrastructure or provide an alternative given the below restrictions: 
  *	Current logon hours defined on their AD need to be abided to for specific roles 
  * Password should not be synced to the cloud 
*	Should not increase number of existing servers for authentication 
*	Minimal change on existing apps and architecture 
*	MFA should not be triggered for specific known scenarios (users in corporate network, users coming from domain-joined devices, etc.) 
*	Access to Workday should be allowed only on corporate domain-joined devices or BYOD managed devices 
*	Need to ensure that all BYOD devices meet a specific level of patching and windows updates to connect to corporate resources 
*	Prevent data leakage between corporate and personal apps on mobile devices 
*	When possible existing unclassified content on SaaS apps should be classified/encrypted  
*	Data should be protected when accessed from unmanaged devices  

# Solutions
* Editing
