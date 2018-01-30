# Symfony 2.8 + Vendors

## Windows

- Clone or download this repository.
- Run `vagrant up`
- Open http://192.168.10.66/app.php/

## OSX / Linux

- Clone or download this repository.
- Activate nfs in the Vagrantfile (`machine.vm.synced_folder ".", "/opt/proj"#, type: "nfs"` (remove the `#`))
- Run `vagrant up`
- Open http://192.168.10.66/app.php/