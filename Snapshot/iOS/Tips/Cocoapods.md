### setting up cocoapods master repo 非常慢的问题解决

第一步：移除tao bao的Ruby源

命令： gem sources --remove https://ruby.taobao.org/

第二步：添加ruby-china

命令：gem source -a https://gems.ruby-china.org/

第三步：查看是否更换成功

命令：gem source

第四步重新安装cocoapods

命令：sudo gem install cocoapods

第五步：初始化pod

命令：pod setup

第六步：查看pod

命令：pod --version