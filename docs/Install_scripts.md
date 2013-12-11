
sudo apt-get install graphviz libgraphviz-dev pandoc

mkvirtualenv  --no-site-packages -p ~/.pyenv/versions/3.3.2/bin/python my3env


== Install ZeroMQ

src:: http://zeromq.org/intro:get-the-software

sudo apt-get install libtool autoconf automake uuid-dev build-essential uuid
wget http://download.zeromq.org/zeromq-4.0.3.tar.gz
tar xzf zeromq-4.0.3.tar.gz
cd zeromq-4.0.3
./configure
make
sudo make install.

On Linux, run sudo ldconfig after installing ØMQ

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the `-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the `LD_LIBRARY_PATH' environment variable
     during execution
   - add LIBDIR to the `LD_RUN_PATH' environment variable
     during linking
   - use the `-Wl,-rpath -Wl,LIBDIR' linker flag
   - have your system administrator add LIBDIR to `/etc/ld.so.conf'

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.


== Setting up environment

workon myenv3
git clone --recursive https://github.com/ipython/ipython.git
cd ipython
python setupegg.py develop
easy_install readline
pip install ipython[test]
pip install pexpect
easy_install ipython[zmq]
pip install Pygments
pip install Jinja2
pip install Sphinx
pip install tornado

easy_install Werkzeug

    at present need this instead for Python 3
git clone https://github.com/philipaxer/pygraphviz.git
python setup.py install


pip install django django-extensions
pip install south
pip install djangorestframework django-cors-headers
pip install django-bootstrap3

django-admin.py startproject mysite


== Using IPython enhanced shell

manage.py shell_plus --notebook
This will open a IPython notebook on your web browser instead of the IPython shell interpreter. Write your code there, and run it.

When you change your modules, just click on the web page menu item 'Kernel->Restart'
