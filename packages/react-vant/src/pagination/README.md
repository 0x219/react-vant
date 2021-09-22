# Pagination 分页

### 介绍

数据量过多时，采用分页的形式将数据分隔，每次只加载一个页面。

### 引入

```js
import { Pagination } from 'react-vant';
```

## 代码演示

### 基础用法

通过 `value` 来绑定当前页码。

```jsx
import { setStatee } from 'react';
import { Pagination } from 'react-vant';

export default () => {
  const [currentPage, setCurrentPage] = useState(1);
  return (
    <Pagination totalItems={24} itemsPerPage={5} value={currentPage} onChange={setCurrentPage} />
  );
};
```

### 简单模式

 将 `mode` 设置为 `simple` 来切换到简单模式，此时分页器不会展示具体的页码按钮。

```jsx
<Pagination value={currentPage} pageCount={12} mode="simple" />
```

### 显示省略号

```jsx
<Pagination value={currentPage} pageCount={12} forceEllipses />
```

### 自定义按钮

通过 `prevText`、`nextText` 等属性来自定义分页按钮的内容。

```jsx
<Pagination
  value={page4}
  onChange={setPage4}
  totalItems={125}
  showPageSize={5}
  prevText={<Icon name="arrow-left" />}
  nextText={<Icon name="arrow" />}
  pageRender={({ text }) => `😀${text}`}
/>
```

## API

### Props

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| value | 当前页码 | _number_ | - |
| mode | 显示模式，可选值为 `simple` | _string_ | `multi` |
| prevText | 上一页按钮文字 | _ReactNode_ | `上一页` |
| nextText | 下一页按钮文字 | _ReactNode_ | `下一页` |
| pageRender | 自定义页码 | _({ number: number, text: string, active: boolean }) => ReactNode_ | - |
| pageCount | 总页数 | _number \| string_ | 根据页数计算 |
| totalItems | 总记录数 | _number \| string_ | `0` |
| itemsPerPage | 每页记录数 | _number \| string_ | `10` |
| showPageSize | 显示的页码个数 | _number \| string_ | `5` |
| forceEllipses | 是否显示省略号 | _boolean_ | `false` |

### Events

| 事件名   | 说明           | 回调参数      |
| -------- | -------------- | ------------- |
| onChange | 页码改变时触发 | _page:number_ |

### 类型定义

组件导出以下类型定义：

```js
import type { PaginationMode } from 'react-vant';
```

## 主题定制

### 样式变量

组件提供了下列 CSS 变量，可用于自定义样式，使用方法请参考 [ConfigProvider 组件](#/zh-CN/config-provider)。

| 名称                                            | 默认值                        | 描述 |
| ----------------------------------------------- | ----------------------------- | ---- |
| --van-pagination-height                         | _40px_                        | -    |
| --van-pagination-font-size                      | _var(--van-font-size-md)_     | -    |
| --van-pagination-item-width                     | _36px_                        | -    |
| --van-pagination-item-default-color             | _var(--van-primary-color)_    | -    |
| --van-pagination-item-disabled-color            | _var(--van-gray-7)_           | -    |
| --van-pagination-item-disabled-background-color | _var(--van-background-color)_ | -    |
| --van-pagination-background-color               | _var(--van-white)_            | -    |
| --van-pagination-desc-color                     | _var(--van-gray-7)_           | -    |
| --van-pagination-disabled-opacity               | _var(--van-disabled-opacity)_ | -    |
