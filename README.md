# toolbox

终端接入校园网账号：https://github.com/hstable/SRUN_LOGIN

在未连入校园网账号时获取 IPv6 地址（绝大多数情况够用）：
```bash
dhclient -6
```

IPv6 可用的 Github 镜像站（git clone 时将 github.com 替换为下列地址）：
```
hub.ip233.cn
```

显示谁在占用 NVIDIA GPU：
```bash
bash -c 'i=1;nvidia-smi --query-compute-apps=pid,process_name,used_memory --format=csv|tail -n +2|while read -r line;do echo "$i: $line";strings /proc/"$(echo $line | cut -d, -f1)"/environ|grep -E --color=never "LOGNAME|^PWD|CONDA_DEFAULT_ENV"|sed "s/^/\t/g";i=$[$i+1];done'
```
