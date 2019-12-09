# Starting/Stopping SCN <a id="starting-stopping-scn"></a>

Depending on your installation type, you can start/stop the Klaytn service with the following `systemctl`  or `kscnd` command.

**실행**

```bash
## when installed from rpm distribution 
$ systemctl start kscnd.service

## when installed using linux archive
$ kscnd start

```

**중지**

```bash
## when installed from rpm distribution 
$ systemctl stop kscnd.service

## when installed using linux archive
$ kscnd stop

```

**status**

```bash
## when installed from rpm distribution 
$ systemctl status kscnd.service

## when installed using linux archive
$ kscnd status

```

