---
layout: post
title: Thin Provisioning Disks in ESX
created: 1220714867
categories:
- esx
- virtualisation
---
<p>Log in over SSH and run:</p> <pre>
vmkfstools -c 50G -d thick /vmfs/volumes/san/vm/thick.vmdk
vmkfstools -c 50G -d thin /vmfs/volumes/san/vm/thin.vmdk
</pre> <p>A ls will show:</p> <pre>
50G thick-flat.vmdk
373 thick.vmdk
50G thin-flat.vmdk
398 thin.vmdk&nbsp;</pre> <p>However a du will show:</p> <pre>
50G   thick-flat.vmdk
64K   thick.vmdk
1.0M  thin-flat.vmdk
64K   thin.vmdk</pre> <p>Which is, I think, rather neat...</p>
