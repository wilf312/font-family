# font-family list
font-family

https://wilf312.github.io/font-family/ に行くといろんなフォント指定を確認することが出来、
ブラウザ上でどのフォントをレンダリングしているかも確認することができます。

thank great npm module https://www.npmjs.com/package/detect-font


|  | Mac Chrome | Mac Firefox | Mac Safari | Win Chrome | Win Firefox | Win IE11 | Win Edge | iOS Safari | android Chrome |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| sans-serif | ○ | ○ | ○ | ○ | ○ | ○ | ○ | ○ | ☓ |
| serif | ○ | ○ | ○ | ○ | ○ | ○ | ○ | ○ | ☓ |
| Meiryo | ○ | ○ | ☓ | ☓ | ☓ | ☓ | ☓ | ☓ | ☓ |
| "メイリオ" | ☓ | ○ | ☓ | ☓ | ☓ | ☓ | ☓ | ☓ | ☓ |
| 'Hiragino Kaku Gothic ProN' | ○ | ○ | ○ | ☓ | ☓ | ☓ | ☓ | ○ | ☓ |
| 'ヒラギノ角ゴ ProN W3' | ☓ | ○ | ○ | ☓ | ☓ | ☓ | ☓ | ○ | ☓ |
| "メイリオ","Hiragino Kaku Gothic ProN",Meiryo,"ヒラギノ角ゴ Pro W3","MS PGothic","MS UI Gothic",Helvetica,Arial,sans-serif | Hiragino Kaku Gothic ProN | メイリオ | Hiragino Kaku Gothic ProN | MS PGothic | MS PGothic | MS PGothic | MS PGothic | Hiragino Kaku Gothic ProN | Helvetica |





## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn run serve
```

### Compiles and minifies for production
```
yarn run build
```

### Run your tests
```
yarn run test
```

### Lints and fixes files
```
yarn run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
