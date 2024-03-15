Create an Ansible Playbook to Cater for Different Versions of Ansible on Different Controllers

sudo apt install python3.8-venv

python3 -m venv old

source old/bin/activate

pip install wheel
pip install 'ansible==2.9.22'

ansible --version

└──╼ $sudo apt install python3.9.2-venv
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
E: Unable to locate package python3.9.2-venv
E: Couldn't find any package by glob 'python3.9.2-venv'
┌─[✗]─[bogdan@parrot]─[~]
└──╼ $sudo apt install python3.9-venv
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
python3.9-venv is already the newest version (3.9.2-1).
python3.9-venv set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 237 not upgraded.
┌─[bogdan@parrot]─[~]
└──╼ $python3 -m venv old
┌─[bogdan@parrot]─[~]
└──╼ $source old/bin/activate
(old) ┌─[bogdan@parrot]─[~]
└──╼ $pip install wheel
Collecting wheel
  Downloading wheel-0.43.0-py3-none-any.whl (65 kB)
     |████████████████████████████████| 65 kB 1.3 MB/s 
Installing collected packages: wheel
Successfully installed wheel-0.43.0
(old) ┌─[bogdan@parrot]─[~]
└──╼ $pip install 'ansible==2.9.22'
Collecting ansible==2.9.22
  Downloading ansible-2.9.22.tar.gz (14.3 MB)
     |████████████████████████████████| 14.3 MB 16.0 MB/s 
Collecting PyYAML
  Downloading PyYAML-6.0.1-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (738 kB)
     |████████████████████████████████| 738 kB 6.2 MB/s 
Collecting cryptography
  Downloading cryptography-42.0.5-cp39-abi3-manylinux_2_28_x86_64.whl (4.6 MB)
     |████████████████████████████████| 4.6 MB 1.1 MB/s 
Collecting jinja2
  Downloading Jinja2-3.1.3-py3-none-any.whl (133 kB)
     |████████████████████████████████| 133 kB 15.9 MB/s 
Collecting cffi>=1.12
  Downloading cffi-1.16.0-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (443 kB)
     |████████████████████████████████| 443 kB 2.4 MB/s 
Collecting pycparser
  Downloading pycparser-2.21-py2.py3-none-any.whl (118 kB)
     |████████████████████████████████| 118 kB 64.7 MB/s 
Collecting MarkupSafe>=2.0
  Downloading MarkupSafe-2.1.5-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (25 kB)
Building wheels for collected packages: ansible
  Building wheel for ansible (setup.py) ... done
  Created wheel for ansible: filename=ansible-2.9.22-py3-none-any.whl size=16204960 sha256=1a941ad5ed8445d80dac92ad3ea18210b7b8c743b23fd2e097eb025e0f648ae1
  Stored in directory: /home/bogdan/.cache/pip/wheels/1b/39/fc/47087368508b2e550a70de5221621f9a6008528f3deabc9404
Successfully built ansible
Installing collected packages: pycparser, MarkupSafe, cffi, PyYAML, jinja2, cryptography, ansible
Successfully installed MarkupSafe-2.1.5 PyYAML-6.0.1 ansible-2.9.22 cffi-1.16.0 cryptography-42.0.5 jinja2-3.1.3 pycparser-2.21
(old) ┌─[bogdan@parrot]─[~]
└──╼ $ansible --version
ansible 2.9.22
  config file = None
  configured module search path = ['/home/bogdan/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /home/bogdan/old/lib/python3.9/site-packages/ansible
  executable location = /home/bogdan/old/bin/ansible
  python version = 3.9.2 (default, Feb 28 2021, 17:03:44) [GCC 10.2.1 20210110]
(old) ┌─[bogdan@parrot]─[~]
