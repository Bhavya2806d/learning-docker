FROM ubuntu

WORKDIR /app

COPY requirements.txt /app/
COPY devops /app/
#copy sourcecode from devops

RUN apt-get update && apt-get install -y python3 python3-pip python3-venv
#-----------
#RUN python3 -m venv venv1 && \
#source venv1/bin/activate
#-----------
#is doing then let me explain

#1st line mean 'RUN python3 -m venv venv1 '
#it will run the command which will create a virtual environment, here venv is a module which will create virtual environment and venv1 is the name of the environment…

#2nd line  mean 'source venv1/bin/activate '
#Once the virtual environment is created, you need to activate it. And bash we use source 'venv1'(which is environment name)/bin/activate

#and the above one line 
#-----  SHELL ["/bin/bash", "-c"]  -----
#is used to set bash as default  else in sh is set by default
SHELL ["/bin/bash", "-c"]

RUN python3 -m venv venv1 && \
source venv1/bin/activate && \
pip install --no-cache-dir -r requirements.txt

EXPOSE 8000

CMD source venv1/bin/activate && python3 manage.py runserver 0.0.0.0:8000




