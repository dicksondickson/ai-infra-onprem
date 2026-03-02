
# LiteLLM proxy gives you a unified OpenAI-compatible endpoint with extras like rate limiting, logging, and model aliasing. 



# install litellm via pip
pip install 'litellm[proxy]'



# make config file
mkdir -p ~/.config/litellm && nano ~/.config/litellm/config.yaml



# run
litellm \
  --config ~/.config/litellm/config.yaml \
  --host 0.0.0.0 \
  --port 20000




# test

curl http://localhost:20000/v1/models



curl http://192.168.50.29:20000/v1/chat/completions \
  -H "Authorization: Bearer llm" \
  -H "Content-Type: application/json" \
  -d '{"model": "qwen3.5-35b-instruct-general", "messages": [{"role": "user", "content": "hello!! OMG!!"}]}'








# BASE URL
http://192.168.50.29:20000/v1


API KEY
llm





# run as service
sudo nano /etc/systemd/system/litellm.service




# paste in file
```
[Unit]
Description=LiteLLM Proxy
After=network.target

[Service]
Type=simple
User=gougou
ExecStart=/home/gougou/.local/bin/litellm --config /home/gougou/.config/litellm/config.yaml --host 0.0.0.0 --port 8901
Restart=on-failure
RestartSec=5

[Install]
WantedBy=multi-user.target
```



# start service

sudo systemctl daemon-reload
sudo systemctl enable litellm
sudo systemctl start litellm




# check
sudo systemctl status litellm

