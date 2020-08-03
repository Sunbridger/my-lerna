
##  安装所有包的所有依赖

lerna bootstrap

咱们 lerna.json中  npmClient 字段指向yarn

所以其作用类似

yarn install

若为 npm 则是 npm install


## 安装每个包的依赖
lerna 加 作用域安装法：

lerna add axios --scope=vu

和在packages/vu中下输入 yarn add axios 的效果是一样的

包的依赖都会共同安装到顶层的node_modules中的

注意 但是lerna 这个命令是全项目的 所以 无论在那个目录下输入

lerna add lodash

结果都是所有的包都安装此依赖



类似总结如下：


```
# Adds the module-1 package to the packages in the 'prefix-' prefixed folders
lerna add module-1 packages/prefix-*

# Install module-1 to module-2
lerna add module-1 --scope=module-2

# Install module-1 to module-2 in devDependencies
lerna add module-1 --scope=module-2 --dev

# Install module-1 in all modules except module-1
lerna add module-1

# Install babel-core in all modules
lerna add babel-core
```

## 发布
lerna publish

会打tag，上传git,上传npm。
