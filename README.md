# certbot

# centos
yum install epel-release -y && yum makecache fast
yum install certbot -y

# 申请单证书
certbot certonly -d mg2.98hg.top --preferred-challenges http --server https://acme-v02.api.letsencrypt.org/directory
# 申请通配符证书
certbot certonly -d mg2.98hg.top --preferred-challenges http --server https://acme-v02.api.letsencrypt.org/directory
交互过程
# 提示输入邮箱，选择Y

# 等到“Please deploy a DNS TXT record under the name”出现后，需要在域名供应商DNS管理添加TXT记录
# 名称为_acme-challenge.gisstack.org（域名替换为自己的），填入提示的value，类似于“WdDIXIrJYROoz80fGsmFau8T0zCPfRBRs-sp6r-Zs3E”这样的一串字符

# 配置好后需要等待生效，一般不超过一分钟

# 确认TXT解析成功后，就可以下一步了，直接回车确认

# 成功后，证书路径为/etc/letsencrypt/live/gisstack.org
