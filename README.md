自动校验发布流程

```yml
# 预发布 vX.Y.Z-(pre/dev/beta/rc) 只检查不发布
# 正式发布 vX.Y.Z 会执行所有检查并使用OIDC的方式发布


on:
  push:
    tags:
      - 'v*.*.*'
      - 'v*.*.*-*.*'

jobs:
  publish:
    uses: aymtools/futter-ci/workflows/publish.yml@main

```

package最低版本限制 只能识别下面样式

```yml
environment:
  sdk: '>=3.4.0 <4.0.0'
  flutter: '>=3.22.0'
```