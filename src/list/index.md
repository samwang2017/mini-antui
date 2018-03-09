## list
| 属性 | 说明 | 类型 | 默认值 |
|----|----|----|----|
|className| 自定义class | String| |

### slots
|slotName | 说明 |
|----|----|
|listHeader | 可选，用于渲染列表头部|
|listItems | 可选，用于渲染列表尾部|
|listFooter | 可选，用于渲染列表项|

### examples

```axml
<list>
  <view slot="listHeader">列表头部</view>
  <view slot="listItems">
    <block a:for="{{items}}">
      <listitem key="item-{{index}}">
        <view slot="content">
          {{item.title}}
          <view class="am-list-brief">{{item.brief}}</view>
        </view>
      </listitem>
    </block>
  </view>
  <view slot="listFooter">列表尾部</view>
</list>
```

## list-item

| 属性 | 说明 | 类型 | 默认值 |
|----|----|----|----|
|className| 自定义的class | String| |
|thumb| 缩略图 | 图片地址 |  |
|arrow| 箭头方向(右,上,下), 可选，`horizontal`,`up`,`down`,`empty`，如果是empty则存在对应的dom,但是不显示 | String | |
|align| 子元素垂直对齐，可选`top`,`middle`,`bottom` | String | `middle` |
|index| | | |
|onClick| | | |

### slots

| slotname | 说明 |
|----|----|
|content | 可选，用于渲染列表项左边内容|
|extra | 可选，用于渲染列表项右边说明|

### examples

```axml
<listitem
  className="{{index === 0 ? 'am-list-sticky' : ''}}"
  thumb="{{item.thumb}}"
  arrow="{{item.arrow}}"
  align="{{item.align}}"
  index="{{index}}"
  onClick="{{onItemClick}}"
  key="items-{{index}}"
>
  <view slot="content">
    {{item.title}}
    <view class="am-list-brief">{{item.brief}}</view>
  </view>
  <view slot="extra">
    {{item.extra}}
  </view>
</listitem>

```