
### Recommended Folder Structure

A typical root directory layout for most software projects includes the following folders and files:[](https://github.com/kriasoft/Folder-Structure-Conventions)​

```
|── src/           # Source code files
├── tests/         # Automated tests
├── docs/          # Documentation (alternatively 'doc')
├── tools/         # Tools and utilities/scripts
├── assets/        # Static resources (images, CSS, etc.)
├── .github/       # GitHub workflows and issue templates
├── LICENSE        # License information
├── README.md      # Project overview and documentation
└── .gitignore     # Git exclusion rules
```


- For multi-component projects, add folders like `/frontend`, `/backend`, and `/scripts` as needed.[](https://github.com/orgs/community/discussions/168684)​
    
- Each main folder (e.g., `src`, `tests`, `docs`) can include a `README.md` explaining its purpose.[](https://github.com/orgs/community/discussions/168684)​
    

### Steps to Initialize and Structure Your Repository

1. **Create Repository on GitHub**  
    Use GitHub’s web interface to create a new repo:
    
    - Click “New repository,” name your project, and add a description.
        
    - Optionally, initialize with a README.[](https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories)​
        
2. **Clone Repository Locally**
    
    `git clone https://github.com/username/project-name.git cd project-name`
    
3. **Create Recommended Folders**
    
    
    `mkdir src tests docs tools assets .github touch README.md LICENSE .gitignore`
    
4. **Add Sample Files**  
    For each folder, add a placeholder file such as a README to allow Git to track it:
    
    
    `echo "Source code files go here" > src/README.md echo "Test files go here" > tests/README.md echo "Documentation goes here" > docs/README.md`
    
5. **Stage and Commit Structure**
    
    
    `git add . git commit -m "Initial project structure with recommended folders" git push origin main`
    


### Best Practices

- Include a top-level README.md for project overview.[](https://docs.github.com/en/repositories/creating-and-managing-repositories/best-practices-for-repositories)​
    
- Use consistent, lowercase names for folders and files.[](https://gitprotect.io/blog/how-to-put-a-project-on-github-best-practices/)​
    
- Add a LICENSE file to specify usage terms.[](https://github.com/kriasoft/Folder-Structure-Conventions)​
    
- Use .gitignore to exclude unnecessary files from Git.[](https://github.com/kriasoft/Folder-Structure-Conventions)​
    
- Place GitHub configuration (workflows, issue templates) in the `.github` folder.
    
- Add documentation and placeholder files in each key folder to help contributors navigate the repo.[](https://worldbank.github.io/template/docs/folders-and-naming.html)​
    

This structure is widely recognized and helps contributors understand your project quickly while making future expansion and automation easier.[](https://worldbank.github.io/template/docs/folders-and-naming.html)​