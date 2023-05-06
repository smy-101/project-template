# compilerOptions

## esModuleInterop

esModuleInterop的作用是让TS能够更好地兼容CommonJS/AMD/UMD模块。设置不设置的区别主要体现在导入这些模块的方式上。

如果不设置esModuleInterop，那么你必须使用星号（*）来导入这些模块，例如：

`import * as React from "react";`

这样做的问题是，它不符合ES6模块规范，因为星号导入的对象不能被调用。

如果设置了esModuleInterop，那么你可以使用默认导入的方式来导入这些模块，例如：

`import React from "react";`

这样做的好处是，它符合ES6模块规范，而且更简洁和直观23。TS会在编译时自动添加一些辅助函数来保证运行时的兼容性。

## module

tsconfig中module项的作用是告诉TS编译器在编译成JS时使用什么样的模块化标准。

可以根据你的项目运行环境和需要的JS特性来选择合适的module。例如，如果你的项目在Node.js中运行，你可能需要选择"CommonJS"；

如果你的项目使用了动态导入或import.meta等特性，可能需要选择"ES2020"或"ESNext"。

## moduleResolution

影响TS编译器如何解析你的模块导入

'node' for Node.js’ CommonJS implementation

'node16' or 'nodenext' for Node.js’ ECMAScript Module Support from TypeScript 4.7 onwards

## jsx

tsconfig中jsx的作用是控制TS编译器在编译成JS时如何处理JSX语法。这只影响从.tsx文件生成的JS文件。TS支持以下几种jsx模式：

react: 生成.js文件，将JSX转换为等价的React.createElement调用。

react-jsx: 生成.js文件，将JSX转换为_jsx调用。这是React 17引入的新形式的JSX转换。

react-jsxdev: 生成.js文件，将JSX转换为_jsxDEV调用。这是React 17引入的新形式的JSX转换，用于开发环境3。

preserve: 生成.jsx文件，保留JSX不变，以供其他转换步骤（如Babel）使用。

react-native: 生成.js文件，保留JSX不变。

## allowUmdGlobalAccess

allowUmdGlobalAccess 是一个 TypeScript 的编译选项，它可以让你在模块文件中访问 UMD 导出的全局变量。

UMD 是一种模块定义的方式，它兼容 AMD、CommonJS 和全局变量三种模式。

如果你没有设置这个选项，那么你需要使用 import 声明来使用 UMD 模块的导出。

一个使用这个选项的场景是，你的 web 项目中有一些库（比如 jQuery 或 Lodash）你知道它们在运行时总是可用的，但是你不能用 import 来访问它们。



