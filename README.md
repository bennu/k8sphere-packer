# k8sphere VM templates

Companion VM templates for k8sphere, built with Packer.

**Note:** This image installs kernel v4.15.x, still you can edit and adjust the image to your needs.

This repo contains 3 flavors:

- [docker](xenial/scripts/docker)
- [containerd](xenial/scripts/containerd)
- [containerd + kata](xenial/scripts/kata)

It reads values from the following env vars:

- `ESXI_DATASTORE` (e.g. `datastore1`)
- `ESXI_HOST` (e.g. `192.168.0.51` or `host1.domain.local`)
- `ESXI_USERNAME` (username for esxi host, recommended other than root)
- `ESXI_PASSWORD` (password for esxi host account, recommended other than root)
- `VSPHERE_DC` (e.g. `DC1`)
- `VSPHERE_HOST` (e.g. `192.168.0.50` or `vcenter.domain.local`)
- `VSPHERE_INSECURE` (set to `true` for self-signed certs)
- `VSPHERE_USERNAME` (username for vcenter user)
- `VSPHERE_PASSWORD` (password for vcenter user account)

Additionaly you can set some debug info while building the image

- `PACKER_LOG=1`
- `PACKER_LOG_PATH="packer.log"`

If VNC connection takes more than usual, you can override the timeout as you please

- `PACKER_ESXI_VNC_PROBE_TIMEOUT=50s`