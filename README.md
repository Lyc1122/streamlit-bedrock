Launch a Ubuntu Machine and open 22 & 8501 PORT

```
sudo apt update
sudo apt-get install python3-pip
sudo apt install python3-venv
```

install AWS CLI
```
sudo apt-get install unzip
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws --version
```
 
active the venv
```
sudo apt install python3-venv
python3 -m venv .venv
source .venv/bin/activate
```
 
clone the streamlit UI
```
git clone https://github.com/Lyc1122/amazon-bedrock-agent-test-ui.git
cd amazon-bedrock-agent-test-ui
pip install -r requirements.txt
```

Set env variables for the streamlit ui's permission
Make sure the associated AWS IAM user has Bedrock permission
```
sudo nano env_vars.sh
export AWS_ACCESS_KEY_ID=the_access_key
export AWS_SECRET_ACCESS_KEY=the_secret_key
export AWS_DEFAULT_REGION=ap-southeast-2
export BEDROCK_AGENT_ID=the_agent_id
export BEDROCK_AGENT_ALIAS_ID=the_alias_id
export BEDROCK_AGENT_TEST_UI_TITLE=the_title_of_the_page
save with control + x
source env_vars.sh
```
run streamlit server and you will see the URL in terminal
```
streamlit run app.py
```

(Optional) run streamlit server in the backend, streamlit will keep running even you disconnected from the EC2 SSH
```
nohup streamlit run app.py
```
