# 用karma测试 Require.js
==================================

需要两个文件：

* `karma.conf.js` &mdash; 设置karma
* `test-main.js` &mdash; 设置Requirejs

测试例子目录如下：

```bash
$ tree
.
|-- index.html
|-- karma.conf.js
|-- lib
|   |-- jquery.js
|   |-- require.js
|   `-- underscore.js
|-- src
|   |-- app.js
|   `-- main.js
`-- test
    |-- appSpec.js
    `-- test-main.js

3 directories, 9 files
```

## 设置karma

命令

```bash
$ karma init
```

* `lib/**/*.js` &mdash; 第三方库
* `src/**/*.js` &mdash; 本地代码
* `test/**/*Spec.js` &mdash; 所有test

如下:

```javascript
// list of files / patterns to load in the browser
files = [
  JASMINE,
  JASMINE_ADAPTER,
  REQUIRE,
  REQUIRE_ADAPTER,

  {pattern: 'lib/**/*.js', included: false},
  {pattern: 'src/**/*.js', included: false},
  {pattern: 'test/**/*Spec.js', included: false},

  'test/test-main.js'
];

// list of files to exclude
exclude = [
    'src/main.js'
];
```

## 设置Requirejs

像Requirejs项目一样，设置入口js文件来启动test：‘test/test-main.js’

```

## 运行测试

```bash
$ npm install
$ npm run test
```
##如果你想实时查看运行结果，运行下面代码：

```bash
$ npm run watch
```