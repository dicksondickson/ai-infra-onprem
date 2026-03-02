

https://github.com/mostlygeek/llama-swap




# install from precompile binaries
# Download latest release (check for current version)


wget https://github.com/mostlygeek/llama-swap/releases/download/v196/llama-swap_196_linux_amd64.tar.gz
tar xzf llama-swap_196_linux_amd64.tar.gz
sudo mv llama-swap /usr/local/bin/






# config

mkdir -p ~/.config/llama-swap && nano ~/.config/llama-swap/config.yaml





# run
# change litellm port settings if using with litellm
llama-swap --config ~/.config/llama-swap/config.yaml --listen 0.0.0.0:2400