Możesz [pominąć tę sekcję](http://tutorial.djangogirls.org/en/installation/#install-python) jeżeli nie korzystasz z Chromebook-a. If you are, your installation experience will be a little different. You can ignore the rest of the installation instructions.

### Cloud 9

Cloud 9 is a tool that gives you a code editor and access to a computer running on the Internet where you can install, write, and run the software. For the duration of the tutorial, Cloud 9 will act as your *local machine*. Można będzie działać polecenia w terminalu interfejs podobnie jak Twoich kolegów na OS X, Ubuntu lub Windows, ale twój terminal będzie podłączony do komputera z systemem gdzieś indziej Cloud 9 ustawia dla Ciebie.

1. Install Cloud 9 from the [Chrome web store](https://chrome.google.com/webstore/detail/cloud9/nbdmccoknlfggadpfkmcpnamfnbkmkcp)
2. Go to [c9.io](https://c9.io)
3. Sign up for an account
4. Click *Create a New Workspace*
5. Name it *django-girls*
6. Select the *Blank* (second from the right on the bottom row with orange logo)

Now you should see an interface with a sidebar, a big main window with some text, and a small window at the bottom that looks something like this:

{% filename %}Cloud 9{% endfilename %}

    yourusername:~/workspace $
    

Ten dolny obszar jest Twój *terminal*, gdzie będzie dać komputerowi Cloud 9 przygotował dla instrukcji. Można zmienić rozmiar tego okna, aby zrobić to nieco większe.

### Środowisko wirtualne

A virtual environment (also called a virtualenv) is like a private box we can stuff useful computer code into for a project we're working on. We use them to keep the various bits of code we want for our various projects separate so things don't get mixed up between projects.

In your terminal at the bottom of the Cloud 9 interface, run the following:

{% filename %}Cloud 9{% endfilename %}

    sudo apt update
    sudo apt install python3.6-venv
    

If this still doesn't work, ask your coach for some help.

Next, run:

{% filename %}Cloud 9{% endfilename %}

    mkdir djangogirls
    cd djangogirls
    python3.6 -mvenv myvenv
    source myvenv/bin/activate
    pip install django~=1.11.0
    

(note that on the last line we use a tilde followed by an equal sign: ~=).

### Github

Make a [Github](https://github.com) account.

### PythonAnywhere

The Django Girls tutorial includes a section on what is called Deployment, which is the process of taking the code that powers your new web application and moving it to a publicly accessible computer (called a server) so other people can see your work.

This part is a little odd when doing the tutorial on a Chromebook since we're already using a computer that is on the Internet (as opposed to, say, a laptop). However, it's still useful, as we can think of our Cloud 9 workspace as a place or our "in progress" work and Python Anywhere as a place to show off our stuff as it becomes more complete.

Thus, sign up for a new Python Anywhere account at [www.pythonanywhere.com](https://www.pythonanywhere.com).