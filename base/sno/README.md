Inside the provisioningoverride manifest we have the disableVirtualMediaTLS parameter which turns off TLS on the virtual media server, which may be required for hardware that cannot accept HTTPS links.

This will either be enabled or disabled using boolean depended on the type of hardware the SNO is being deployed on. 

The patch to enable and disable it is part of vse-ocp-bases/overlay/sno/kustomization.yaml 

The parameter is disabled by default.
