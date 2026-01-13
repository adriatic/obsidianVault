This is the simplest PRB Demo testing definition, which will later become a part of PRB testing  *(note the difference between PRB demo testing that should take place ASAP, and actual testing examples that should be the part of PRB product)*

The assumptions are

### 1. There is the Gmail and Bitwarden account for the user PRB (defined by its gmail account prbdemo8@gmail.com email)

![[Pasted image 20251229202806.png]]

### 2. The description of the process to create the Github repo that is to be used in PRB demo is:

The user prbdemo8@gmail.com logs in the browser (let's use Chrome for all these testings) activates Bitwarden via its browser Icon as shown below

![[Pasted image 20260101123514.png]]


Here is the view of Bitwarden as activated from browser (see image above)

![[activating a test 2.png]]

Now, this user (who is a fictitious Bitwarden user) has its credentials in all 5 example sites that are already created - but incorrectly, as I did not describe the testing process completely (this is being done now).

**NOTE** initially we will use userID and Password (PrbDemo / PRBDemo2025+) to access the Bitwarden and store the credentials to all 5 test sites. In the real implementation we will have to use all supported Bitwarden user credentials.

### 3. Testing process

Here is a sketch of testing configuration, where the PrbDemo User wants to change the credentials on 3 sites (imagine that this used got the message how its credentials on Site 1, Site 2, Site 3) are possibly stolen and the user needs to replace the credentials ASAP

![[Pasted image 20260101130940.png]]

### 4. Definition of the process to create 5 websites to be used in this testing is:

##### WE ARE NOT SELF HOSTING Bitwarden to provide most realistic PRB app demo​

Create 5 free sites that exercise “state‑of‑the‑art” authentication by combining static hosting (GitHub Pages / Netlify) with WebAuthn demo backends or self‑hosted WebAuthn demos on localhost/containers. The key is that Bitwarden only needs realistic front‑ends and real origins (HTTPS + domains), not production‑grade auth backends.[pages.github+5](https://pages.github.com/)

Since Github Pages do not support authentication -- anything that “protects” pages purely with front‑end JavaScript can be bypassed, since users can still fetch the static assets.[](https://www.reddit.com/r/github/comments/z7gbly/best_way_for_newbie_to_password_protect_a_github/)​). In order to not spend money on such demo sites, we will put an auth proxy in an auth proxy in front. Most likely we will use Cloudflare ensuring that from the browser’s point of view, the origin is still your GitHub Pages domain, so Bitwarden sees a normal HTTPS site but users must authenticate to Cloudflare first.[](https://github.com/orgs/community/discussions/60690)

Alternatively we can consider Prebuilt GitHub Pages + Auth0 bootstrappers:

- [progrium/gh-pages-auth](https://github.com/progrium/staticsite) – Template that wires Auth0 + GitHub OAuth to a GitHub Pages site, exposing a JS API (`login`, `logout`, `isAuthenticated`, etc.).[](https://github.com/progrium/gh-pages-auth)​
    
- [progrium/authsite](https://prowebsitegroup.com/) – Similar tool (`authsite`) that configures Auth0 + Pages and deploys an auth module for use from your static SPA.[](https://github.com/progrium/staticsite)​

These give you a realistic login flow (good enough to test Bitwarden’s interaction with forms and redirects), but remember the underlying static files remain fetchable if someone bypasses the JS.[](https://www.reddit.com/r/github/comments/z7gbly/best_way_for_newbie_to_password_protect_a_github/)






