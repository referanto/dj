# Virtual environmen
To create a virtual environment within this new directory use the format:
```sh
python -m venv <name_-of_env>
```
on Windows, or
<br/>
```sh
python3 -m venv <name_of_env>
``` 
on macOS.

```
% python3 -m venv .venv
% source .venv/bin/activate
(.venv) %
```

# Install Django
```
(.venv) > python -m pip install --upgrade pip
(.venv) > python -m pip install django~=4.0.0
```

# First Django Project
```(.venv) > django-admin startproject django_project .```
```
(.venv) % python3 manage.py runserver
(.venv) > deactivate #deactivate venv
```
# Install Git
On macOS, installing Git via Xcode is currently the easiest option. To check if Git is already
installed on your computer, type git --version in a new terminal window.
```
% git --version
```
then using Git:
```
(.venv) > git init
(.venv) > git status
```
Note that our virtual environment .venv is included which is not a best practice. It should be
kept out of Git source control since secret information such as API keys and the like are often
included in it. The solution is to create a new file called .gitignore which tells Git what to
ignore
```
.gitignore:
.venv/
```
At the same time, we do want a record of packages installed in our virtual environment. 
The current best practice is to create a requirements.txt file with this information.
```
(.venv) > pip freeze > requirements.txt
```
Use Git:
```
(.venv) > git add -A
(.venv) > git commit -m "initial commit"
```

# Create a remote repository
It’s a good habit to create a remote repository of your code for each project. This way you
have a backup in case anything happens to your computer and more importantly, it allows for
collaboration with other software developers.

Sign up for a free account on GitHub’s homepage and verify your email address. Then navigate
to the “Create a new repository” page located at https://github.com/new

Enter the repository name and click on the radio button next to “Private” rather
than “Public.” Then click on the button at the bottom for “Create Repository.”

Your first repository is now created! However there is no code in it yet. Scroll down on the page
to where it says “…or push an existing repository from the command line.” That’s what we want.

Copy the text immediately under this headline and paste it into your command line. Here is what
it looks like for me with my GitHub username of wsvincent. Your username will be different.
```
> git remote add origin https://github.com/wsvincent/hello-world.git
> git branch -M main
> git push -u origin main
```
Assuming everything worked properly, you can now go back to your GitHub webpage and refresh
it. Your local code is now hosted online!
