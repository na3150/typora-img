# Vagrant

## Vagrantfile 생성
```
vagrant init <IMAGE>
```

## VM 생성 및 부팅
```
vagrant up [VM_NAME]
```

## VM 재부팅
```
vagrant reload [VM_NAME]
```

## VM 종료
```
vagrant halt [VM_NAME]
```

## VM 삭제
```
vagrant destroy [VM_NAME]
```

## VM SSH 접속
```
vagrant ssh [VM_NAME]
```

## Vagrantfile 예제
```ruby
Vagrant.configure("2") do |config|
	# Define VM
	config.vm.define "myvm1" do |centos|
		centos.vm.box = "centos/7"
		centos.vm.hostname = "myvm1"
		centos.vm.network "private_network", ip: "192.168.56.11"
		centos.vm.provider "virtualbox" do |vb|
			vb.name = "myvm1"
			vb.cpus = 2
			vb.memory = 2048
		end
		config.vm.provision "shell", inline: <<-SHELL
			#!/bin/bash
			echo "hello world" > /tmp/hello.txt
		    SHELL
	end
end
	# Define VM
	config.vm.define "myvm2" do |centos|
		centos.vm.box = "centos/7"
		centos.vm.hostname = "myvm2"
		centos.vm.network "private_network", ip: "192.168.56.12"
		centos.vm.provider "virtualbox" do |vb|
			vb.name = "myvm2"
			vb.cpus = 2
			vb.memory = 2048
		end
		config.vm.provision "shell", inline: <<-SHELL
			#!/bin/bash
			echo "hello world" > /tmp/hello.txt
		SHELL
	end
end
```



![3학년2학기 시간표](https://raw.githubusercontent.com/na3150/typora-img/main/img/3%ED%95%99%EB%85%842%ED%95%99%EA%B8%B0%20%EC%8B%9C%EA%B0%84%ED%91%9C.jpg?token=APP4GGNIIJIOMPGVOG3OYUDCKQOFQ)