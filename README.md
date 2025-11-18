# NixOSFlake

Defines the flakes for building our operating systems with NixOS.

Each piece of hardware (laptop, desktop, etc...) will each have a NixOS defined in the top level `flake.nix`. For example "TheGrantCube" is Grant Danna's gaming rig.

If you wish to update the flake to the latest version of nix packages, run the following command.

``sudo nix flake update``

If you wish to rebuild your NixOS, run the following command below. Note that in the example I will use "TheGrantCube", but when you run the command you should specifiy your specific hardwares configuration.

``sudo nixos-rebuild switch --flake .#TheGrantCube``

If you wish to mark for deletion previous builds of your NixOS that have been accumulating on your system, run the following command. This will leave your latest NixOS and the second to last build on your system, but mark everything else.

``sudo nix-env -p /nix/var/nix/profiles/system --delete-generations +1``

To delete the previous builds you may have marked, run the following command.

``nix-collect-garbage -d``