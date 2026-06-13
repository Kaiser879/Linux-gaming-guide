## Amd drivers
- if you have a amd driver congratulations you are in luck . there is no need to install drivers seperately because the open source drivers are already baked into the kernal 
- to make sure that amd drivers are loaded
- ```bash
  lspci -k | grep -A 3 VGA //run this 
  ```
- output should be "Kernel driver in use: amdgpu" 
- if not 
- ```bash
  sudo pacman -S mesa vulkan-radeon lib32-mesa lib32-vulkan-radeon //run these to install amd drivers
  ```

## NVIDIA drivers
- Your default Cachy OS system will come with open source NVIDIA  drivers baked in but for optimal performance and better support it is recommended to use proprietary NVIDIA drivers that need installation
- First identify which Nvidia card you have 
| GPU Architecture | Example GPUs | Driver |
|------------------|--------------|----------|
| Blackwell | RTX 5060, RTX 5070, RTX 5080, RTX 5090 | `nvidia-open` |
| Ada Lovelace | RTX 4060, RTX 4070, RTX 4080, RTX 4090 | `nvidia-open` or `nvidia-580xx-dkms` |
| Ampere | RTX 3050, RTX 3060, RTX 3070, RTX 3080, RTX 3090,RTX 2050 | `nvidia-open` or `nvidia-580xx-dkms` |
| Turing | GTX 1650, GTX 1660, RTX 2060, RTX 2080 Ti | `nvidia-open` or `nvidia-580xx-dkms` |
| Volta | Titan V | `nvidia-580xx-dkms` |
| Pascal | GTX 1050, GTX 1060, GTX 1070, GTX 1080 Ti | `nvidia-580xx-dkms` |
| Maxwell | GTX 750 Ti, GTX 960, GTX 970, GTX 980 Ti | `nvidia-580xx-dkms` |
| Kepler | GTX 660, GTX 680, GTX 780 Ti | `nvidia-470xx-dkms` |
| Fermi | GTX 460, GTX 560 Ti, GTX 580 | `nvidia-390xx-dkms` |
| Tesla | GTX 260, GTX 280 | `nvidia-340xx-dkms` |
- these are the respective drivers of your card

### Installing Nvidia drivers
#### For Blackwell cards:
```bash
sudo pacman -S linux-cachyos-nvidia-open
sudo pacman -S nvidia-utils lib32-nvidia-utils nvidia-settings
```

#### For Ada Lovelace
```bash
sudo pacman -S linux-cachyos-nvidia-open
sudo pacman -S nvidia-utils lib32-nvidia-utils nvidia-settings
```

#### For Ampere
```bash
sudo pacman -S linux-cachyos-nvidia-open
sudo pacman -S nvidia-utils lib32-nvidia-utils nvidia-settings
```

#### For Turing
```bash
sudo pacman -S linux-cachyos-nvidia-open
sudo pacman -S nvidia-utils lib32-nvidia-utils nvidia-settings
```
IF you face power-management issues on Turing card 
```shell
yay -S nvidia-580xx-dkms //install 580 drivers insted 
```

#### For pascal
```bash
yay -S nvidia-580xx-dkms 
```

#### For Maxwell
```bash
yay -S nvidia-580xx-dkms 
```

#### For Kepler
```bash
yay -S nvidia-470xx-dkms
```

#### For Fermi
```bash
yay -S nvidia-390xx-dkms
```

#### For Tesla 
```bash
yay -S nvidia-340xx-dkms
```

Reboot after completing installation


### Verifying driver
```bash
nvidia-smi //run this 
```
- Output should show you your current driver version installed , and your card
- make sure that you have the correct driver for your family of card installed

