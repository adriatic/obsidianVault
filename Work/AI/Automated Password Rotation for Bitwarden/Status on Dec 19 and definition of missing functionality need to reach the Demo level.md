I do not believe that this tool have to be integrated into Bitwarden, nor do I believe that Bitwarden will accept such move. Instead it should be standalone tool made available for Bitwarden users as an independent tool, initially hosted by us and announce it in the [Bitwarden Community Forums](https://community.bitwarden.com/?_gl=1*23vpnq*_gcl_au*MTI1MTc1Njk4Ny4xNzY2MDMyNjAz) (we should yet find how to get in there, without pissing off Bitwarden)

Check [What is Bitwarden](/Users/nik/Documents/Obsidian Vault/Work/AI/Automated Password Rotation for Bitwarden/On Bitwarden)
) 

### Bitwarden UI
The Full Bitwarden UI is 

![[Full UI.png|600]]


### Simplest model of Bitwarden Password Rotation (BPR)

I propose that we build BPR as a web application and access it via the toolbar icon as shown below:


This image defines the method of invoking BPR via its own icon (needs to be created) - indicating that the user should use Bitwarden's master password. We will show alternatives to that mode of authentication later. 


We will initially create the smaller version - well suitable for BPR. This UI is inspired by  Bitwarden UI rendered when the user is  authenticated to the BPR, and the UI invoked from the Browser's pinned icons

![[Pasted image 20251219161950.png|250]]

Note that hid my own Bitwarden accounts and observe the needed fields:
1. Search
2. Folder
3. Type




Some initial requirements:

1. Any user of the Bitwarden Password Rotation (BPR) has to have Bitwarden Account (meaning that will have access to his own section of Bitwarden Vault)
2. Define the minimal subset of Bitwarden API needed for PRB correct functioning.
3. 

