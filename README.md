# Crust node
Official crust node service for running crust protocol.

## Preparation work
- Hardware requirements: 

  CPU must contain **SGX module**, and make sure the SGX function is turned on in the bios, please click [this page](https://github.com/crustio/crust/wiki/Check-TEE-supportive) to check if your machine supports SGX

- Operating system requirements:

  Ubuntu 16.04/18.04
  
- Other configurations

  - **Secure Boot** in BIOS needs to be turned off
  - Need use ordinary account, **cannot support root account**

## Install dependencies

### Install crust service
```shell
sudo ./install.sh
```

### Generate application configuration

#### Modify config.yaml
```shell
sudo vim /opt/crust/crust-node/config.yaml
```

### Run crust service and karst service

- Please make sure the following ports are not occupied before starting：
  - 30333 9933 9944 (for crust chain)
  - 56666 (for crust API)
  - 12222 (for crust sWorker)
  - 17000 (for karst)


```shell
sudo systemctl start karst # if you set karst 'enable' in config.yaml
sudo systemctl start crust
```

### Stop crust service and karst service
- Need to stop crust first, then stop karst

```shell
sudo systemctl stop crust
sudo systemctl stop karst # if you set karst 'enable' in config.yaml
```

## License

[GPL v3](LICENSE)
