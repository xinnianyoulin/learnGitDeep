# 仿微信图片预览组件 image-preview

## 使用方式

### 引入

```javascript
import ImagePreview from '@/components/image-preview'

Vue.use(ImagePreview)
```

### 使用

```javascript
this.$imagePreview(options)
```

### options

> Array

图片对象中src为预览实际地址，w、h为图片宽高
PhotoSwipe 本身要求设置宽高，image-preview组件会对没有设置宽高的图片先加载再显示，可能会造成性能问题

```javascript
const images = [
  {
    src: 'http://ww1.sinaimg.cn/large/663d3650gy1fplwvqwuoaj20xc0p0t9s.jpg',
    w: 1200,
    h: 900
  },
  {
    src: 'http://ww1.sinaimg.cn/large/663d3650gy1fplwwcynw2j20p00b4js9.jpg'
  },
  {
    src: require('@/assets/img.jpg')
  }
]

this.$imagePreview(images)
```

> Object

指定图片显示可以通过改变startPosition来实现

```javascript
const options = {
  images: [], // 图片列表，格式同上
  startPosition: 0, // 默认开始播放索引
  showDot: true, // 是否显示底部索引
  spacing: 0.05, // 图片之间的间距比。例如，0.12将渲染为滑动视口宽度的12％（圆角）
  bgOpacity: 1, // 背景遮罩层透明度
  loop: false, // 是否循环播放
  preload: [1, 1], // 懒加载图片个数，arr[0]为当前图片前几张，arr[1]为当前图片后几张
  showHideOpacity: false, // 当缩略图宽高比例与视图不相等时可以开启此项
  thumbClass: 'image-preview' // 缩略图class，添加在缩略图容器上（用来开启缩放动画）
}

this.$imagePreview(options)
```
