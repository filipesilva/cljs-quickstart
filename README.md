# Clojurescript quickstart

## Install on linux
<https://clojure.org/guides/getting_started>


## Install on windows
<https://github.com/clojure/tools.deps.alpha/wiki/clj-on-Windows>


## Issues
optimizations seems to have a windows path bug
```
PS D:\sandbox\cljs-quickstart> clj -m cljs.main --optimizations advanced -c hello-world.core
Exception in thread "main" java.nio.file.InvalidPathException: Illegal char <:> at index 2: /D:/sandbox/cljs-quickstart/out/cljs/core.js
        at java.base/sun.nio.fs.WindowsPathParser.normalize(WindowsPathParser.java:182)
        at java.base/sun.nio.fs.WindowsPathParser.parse(WindowsPathParser.java:153)
        at java.base/sun.nio.fs.WindowsPathParser.parse(WindowsPathParser.java:77)
        at java.base/sun.nio.fs.WindowsPath.parse(WindowsPath.java:92)
        at java.base/sun.nio.fs.WindowsFileSystem.getPath(WindowsFileSystem.java:229)
        at com.google.javascript.jscomp.SourceMapResolver.getRelativePath(SourceMapResolver.java:102)
        at com.google.javascript.jscomp.SourceMapResolver.extractSourceMap(SourceMapResolver.java:63)
        at com.google.javascript.jscomp.JsAst.parse(JsAst.java:169)
        at com.google.javascript.jscomp.JsAst.getAstRoot(JsAst.java:56)
        at com.google.javascript.jscomp.CompilerInput.getAstRoot(CompilerInput.java:125)
        at com.google.javascript.jscomp.Compiler.hoistNoCompileFiles(Compiler.java:2024)
        at com.google.javascript.jscomp.Compiler.orderInputs(Compiler.java:1849)
        at com.google.javascript.jscomp.Compiler.parseInputs(Compiler.java:1755)
        at com.google.javascript.jscomp.Compiler.parseForCompilationInternal(Compiler.java:957)
        at com.google.javascript.jscomp.Compiler.access$300(Compiler.java:109)
        at com.google.javascript.jscomp.Compiler$6.call(Compiler.java:939)
        at com.google.javascript.jscomp.Compiler$6.call(Compiler.java:936)
        at com.google.javascript.jscomp.CompilerExecutor$2.call(CompilerExecutor.java:102)
        at java.base/java.util.concurrent.FutureTask.run(FutureTask.java:264)
        at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)
        at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)
        at java.base/java.lang.Thread.run(Thread.java:834)
```

Running `java -cp "cljs.jar;src" cljs.main --optimizations advanced -c hello-world.core` instead works.