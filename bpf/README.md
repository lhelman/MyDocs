
# BPF y eBPF

## Links
https://github.com/iovisor/bpftrace
https://github.com/iovisor/bcc


## Install Ubuntu 18.04 from source
```for i in bpftrace bcc; do git clone https://github.com/iovisor/$i; done

sudo apt-get -y install bison build-essential cmake flex git libedit-dev   libllvm6.0 llvm-6.0-dev libclang-6.0-dev python zlib1g-dev libelf-dev
sudo apt-get -y install luajit luajit-5.1-dev
sudo apt-get -y install python3-distutils python-distutils
sudo apt-get -y install arping netperf iperf3 iperf
mkdir bcc/build; cd bcc/build
cmake ..
make
sudo make install
cmake -DPYTHON_CMD=python3 .. # build python3 binding
pushd src/python/
make
sudo make install
popd

cd

mkdir bpftrace/build; cd bpftrace/build;
cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr ..
make -j8
sudo make install


```

bcc is on /usr/share/bcc

