## Automated TWRP compilation based on Github Action

## Advertising

1. OrangeFox is [here](https://github.com/azwhikaru/Action-OFRP-Builder)

## 通知

1. Github Actions 服务**不是**无限的，因此为避免浪费，请不要在此中使用未经验证的源代码，这是用于自动化已经稳定的存储库构建的最佳方法

2. 在进行任何更改之前，请确保您正在操作的存储库属于您。如果要提交代码，请使用 **"Fork" 否则使用“使用此模板”**

3. 问题和拉取 **请求可能不会得到** 回复。如果您认为确实有必要，请使用我的个人资料中的电子邮件与我联系。

4. Debian （Ubuntu） 中的 Python 2 已被 **删除**。如果您使用的是 Android 8.1 及更低版本，请使用 *Recovery Build (旧版)*

5. 不要问任何关于你的源代码的问题，比如
	- 没有规则要如何制定......
	- Image ... 尺寸过大

## 谢谢至

所有贡献者

## 参数说明

| 名字                 | 描述                                              | 示例                                                         |
| -------------------- | ------------------------------------------------- | ------------------------------------------------------------ |
| `MANIFEST_URL`       | 源地址                                            | https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git |
| `MANIFEST_BRANCH`    | 源分支                                            | twrp-12.1                                                    |
| `DEVICE_TREE_URL`    | 设备地址                                          | https://github.com/TeamWin/android_device_asus_I003D         |
| `DEVICE_TREE_BRANCH` | 设备分支                                          | android-12.1                                                 |
| `DEVICE_PATH`        | 设备位置                                          | device/asus/I003D                                            |
| `COMMON_TREE_URL`    | 常用树地址                                        | https://github.com/TeamWin/android_device_asus_sm8250-common |
| `COMMON_PATH`        | 常见树位置                                        | device/asus/sm8250-common                                    |
| `DEVICE_NAME`        | 型号名称                                          | I003D                                                        |
| `MAKEFILE_NAME`      | Makefile 名称                                     | twrp_I003D                                                   |
| `BUILD_TARGET`       | 构建目标分区 (boot/recovery/vendorboot)           | recovery                                                     |

-----

## 如何使用

```
例如，您的用户名是：JohnSmith
```

#### 0. 如果要提交代码，请单击此存储库右上角的“Fork”

![image](https://user-images.githubusercontent.com/37921907/177914706-c92476c5-7e14-4fb3-be94-0c8a11dae874.png)

#### 1. 如果您只想简单地使用它，请单击此存储库右上角的“使用此模板”

![image](https://github.com/azwhikaru/Action-TWRP-Builder/assets/37921907/fae6ce3c-bd4c-4bbe-8050-5dd29dff2522)

#### 2. 等待自动重定向后，您将看到自己的用户名

![image](https://user-images.githubusercontent.com/37921907/177915106-5bde6fc9-303c-479e-b290-22b48efd1e4e.png)

#### 3. 更改[用户名和电子邮件](/.github/workflows/Recovery%20Build.yml#L100-L101) 在工作流中重设为您的Github凭据（可选）

## 设置SSH密钥（可选）

#### 4. 转到设置，然后选择部署密钥并选择“添加部署密钥”按钮。

#### 5. 在您的Android设备上，安装[Termux](https://github.com/termux/termux-app/releases)

#### 6. 在Termux中安装openssh并生成ssh密钥。（不要使用密码作为密钥）

注意：为存储库创建部署密钥时，如git@github.com：owner/repo.git或https://github.com/owner/repo，将该URL放入关键注释中。（提示：尝试ssh-keygen…-C”git@github.com：owner/repo.git”。）

owner=您的Github用户名

```
pkg安装openssh
ssh-keygen -t ed25519 -C "git@github.com:owner/Action-Recovery-Builder.git"
```

#### 7. 将密钥添加到您的仓库中。在Termux中，使用以下命令：

```
cd /data/data/com.termux/files/usr/etc/ssh
cat ssh_host_ed25519_key.pub
```

  选择并复制密钥，然后粘贴到“密钥”框中。
  你可以为它命名任何你选择的标题。

#### 8. 现在添加您的私人ssh密钥。回到Termux：

```
cat ssh_host_ed25519_key
```

   复制Termux的输出。



在浏览器中，选择“安全”选项卡下的“机密”。

选择操作选择新存储库密钥对于新密钥名称，
它应该是SSH_PRIVATE_KEY
将SSH_host_ed25519_KEY的输出粘贴到值框中。
然后选择添加密钥。

## 开始构建 Recovery

#### 9. 单击 'Actions-恢复构建'

![image](https://user-images.githubusercontent.com/37921907/177915304-8731ed80-1d49-48c9-9848-70d0ac8f2720.png)

#### 10. 单击 'Run workflow' 并按照上述“参数说明”填写

![image](https://user-images.githubusercontent.com/37921907/177915346-71c29149-78fb-4a00-996f-5d84ffc9eb8c.png)

#### 11. 填写完毕后，点击'Run workflow' 开始运行

-----

## 编译结果

可在以下网址下载 [Release](../../releases)

-----
