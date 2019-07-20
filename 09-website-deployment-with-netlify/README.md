# Website Deployment With Netlify (FREE)

## How It Works
**[Netlify](https://www.netlify.com/)** is a platform for hosting static website such as front end application that uses JavaScript framework like react, vue.js, and etc.

**[Git]((https://www.git-scm.com/))** is a version control system and a must learned for a developer, 95% of dev companies use git.

**[Github](https://github.com/)** is a storage for repository/codes

Manage forms and submissions without any server-side code or JavaScript.

## Git & Pushing To Github
Make sure git is installed

```sh
git --version
```

### Git Commands
```sh
# Initialize a repo
git init

# Add to local repo
git add .

# Commit to local repo
git commit -m 'Initial Commit'

# Add remote github repo
git remote add origin https://github.com/USERNAME/REPO.git

# Initial push
git push -u origin master

# Pushes after initial
git push
```

## Netlify Deploy & Form Submission
_New site from Git_ to add a project, then select provider like Github, Gitlab, Bitbucket.

Update form to use netlify built-in form handling.
```html
<form name="contact" method="POST" data-netlify="true">
```

## Custom Domain Name
To point the root domain at our servers, there are two options
1. **Recommended**: Use a DNS provider that supports CNAME flattening, ANAME or ALIAS. Netlify recommend NS1, or Netlify's built-in DNS.
2. **Alternative**: Create an A record pointing your root domain to our load balancer's IP address **104.198.14.52**.