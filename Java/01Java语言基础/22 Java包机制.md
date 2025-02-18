# 包

## 1 基本概念
包我们每天建的项目就是在一个目录下，我们每次都会建立一个包，这个包在磁盘下其实就是一个目录。**包是用来分门别类的管理技术，不同的技术类放在不同的包下**，方便管理和维护。

**包名的命名规范**：

```
路径名.路径名.xxx.xxx
// 例如：com.github.krislinzhao
```

- 包名一般是公司域名的倒写。例如：黑马是www.github.com,包名就可以定义成com.github.技术名称。
- 包名必须用''."连接。
- 包名的每个路径名必须是一个合法的标识符，而且不能是Java的关键字。

## 2 权限修饰符

在Java中提供了四种访问权限，使用不同的访问权限修饰符修饰时，被修饰的内容会有不同的访问权限，我们之前已经学习过了public 和 private，接下来我们研究一下protected和缺省（default默认）修饰符的作用。

- public：公共的，所有地方都可以访问。
- protected：当前类 ，当前包，当前类的子类可以访问。
- 缺省（没有修饰符）：当前类 ，当前包可以访问。
- private：私有的，当前类可以访问。
  `public > protected > 缺省 > private`

## 3 不同权限的访问能力


|                  | public | protected | 缺省（空的） | private |
| ---------------- | ------ | --------- | ------------ | ------- |
| 同一类中         | √      | √         | √            | √       |
| 同一包中的类     | √      | √         | √            |         |
| 不同包的子类     | √      | √         |              |         |
| 不同包中的无关类 | √      |           |              |         |

可见，public具有最大权限。private则是最小权限。

编写代码时，如果没有特殊的考虑，建议这样使用权限：

- 成员变量使用`private` ，隐藏细节。
- 构造方法使用` public` ，方便创建对象。
- 成员方法使用`public` ，方便调用方法。

> 小贴士：不加权限修饰符，就是default权限