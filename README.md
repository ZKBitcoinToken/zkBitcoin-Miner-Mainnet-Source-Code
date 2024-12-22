# zkBitcoin-Miner-Mainnet-Source-Code
 The source code for zkBitcoin Miner is here
Grab the Folder zkBitcoin Miner- Release Ready - Mainnet v05

Then do this script

# install Ubuntu then run these commands

`sudo apt install curl`

`sudo apt update && sudo apt upgrade -y`

`sudo reboot`

`sudo apt install build-essential cmake git -y`

`curl 'http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1-1ubuntu2.1~18.04.23_amd64.deb' -O`

`sudo dpkg -i libssl1.1_1.1.1-1ubuntu2.1~18.04.23_amd64.deb`

`curl 'https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb' -O`

`sudo dpkg -i packages-microsoft-prod.deb`

`sudo apt update`

`sudo apt install -y dotnet-sdk-5.0`



`curl 'https://developer.download.nvidia.com/compute/cuda/12.5.0/local_installers/cuda-repo-debian12-12-5-local_12.5.0-555.42.02-1_amd64.deb' -O`

`sudo dpkg -i cuda-repo-debian12-12-5-local_12.5.0-555.42.02-1_amd64.deb`

`sudo cp /var/cuda-repo-debian12-12-5-local/cuda-*-keyring.gpg /usr/share/keyrings/`

`sudo add-apt-repository contrib`

`sudo apt-get update`

`sudo apt-get -y install cuda-toolkit-12-5`

`git clone https://github.com/lwYeo/SoliditySHA3Miner.git`

`cd SoliditySHA3Miner`

`curl 'https://raw.githubusercontent.com/ZKBitcoinToken/zkBitcoin-Miner-Mainnet-Source-Code/main/fixes.diff' -O`

`patch -p1 < fixes.diff`

THEN WE ALSO NEED TO DO RECENT VERSION OF CUDA SO DO THIS
open CudaSoliditySHA3Miner/CMakeLists.txt

Make it look like this

   -gencode arch=compute_50,code=sm_50

   -gencode arch=compute_52,code=sm_52

   -gencode arch=compute_61,code=sm_61

   -gencode arch=compute_70,code=sm_70

   -gencode arch=compute_75,code=sm_75

   -gencode arch=compute_80,code=sm_80

   -gencode arch=compute_86,code=sm_86
   
   -gencode arch=compute_89,code=sm_89

   -gencode arch=compute_90,code=sm_90





Then conintue with the rest of the code

`dotnet build SoliditySHA3Miner/SoliditySHA3Miner.csproj -f net5.0 -c Release -o miner`

`cd CudaSoliditySHA3Solver`

`mkdir build`

`cd build`

`cmake ..`

`make`

`cp bin/Release/CudaSoliditySHA3Solver.so ../../miner/`

`cd ../../CPUSoliditySHA3Solver/`

`mkdir build`

`cd build`

`cmake ..`

`make`

`cp bin/Release/CPUSoliditySHA3Solver.so ../../miner/`


`curl 'https://github.com/Microsoft/LightGBM/releases/download/v2.0.12/AMD-APP-SDKInstaller-v3.0.130.136-GA-linux64.tar.bz2' -O`


`tar -xjf AMD-APP-SDKInstaller-v3.0.130.136-GA-linux64.tar.bz2`


`./AMD-APP-SDK-v3.0.130.136-GA-linux64.sh`



#install the script. there maybe an issue where u need to copy home/AMDAPPSDK-3.0/lib/sdk/libOpenCL.so.1 to home/AMDAPPSDK-3.0/lib/libOpenCL.so

then should run

`cd ../../OpenCLSoliditySHA3Solver/`

`mkdir build`

`cd build`

`cmake ..`

`make`

`cp bin/Release/OpenCLSoliditySHA3Solver.so ../../miner/`

`cd ../../miner`

`curl 'https://raw.githubusercontent.com/ZKBitcoinToken/Linux-CPU-GPU-zkBitcoin-Miner/main/Linux%20zkBTC%20Mainnet%20Miner%20v05/ERC-20.abi' -O`

`curl 'https://raw.githubusercontent.com/ZKBitcoinToken/Linux-CPU-GPU-zkBitcoin-Miner/main/Linux%20zkBTC%20Mainnet%20Miner%20v05/zkBTC.abi' -O`

``
