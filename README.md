

## 安装

```
npm install @shawbs/ms-ui -S
```

### 全部引入

```
import MsUi from "@shawbs/ms-ui";
import "@shawbs/ms-ui/lib/theme/index.css";
Vue.use(MsUi, { size: "small" });
```

### 按需引入
```
//.babelrc 
{
    "plugins": [
        [
        "component",
        {
            libraryName: "@shawbs/ms-ui",
            styleLibraryName: "theme",
        }
        ]
    ]
}
```
```
import {
  Tabbar,
  TabbarItem,
  Layout,
  Button,
  ButtonGroup,
  Row,
  Col,
  Icon,
  Popup,
  MessageBox,
  Toast,
  Loading,
  Form,
  FormItem,
  Input,
  Img,
  Link,
  Radio,
  RadioGroup,
  SideMenu
} from "@shawbs/ms-ui";

Vue.component(Tabbar.name, Tabbar);
Vue.component(TabbarItem.name, TabbarItem);
Vue.use(Layout);
Vue.component(Button.name, Button);
Vue.component(ButtonGroup.name, ButtonGroup);
Vue.component(Icon.name, Icon);
Vue.component(Row.name, Row);
Vue.component(Col.name, Col);
Vue.component(Popup.name, Popup);
Vue.use(MessageBox);
Vue.use(Toast);
Vue.use(Loading);
Vue.component(Form.name, Form);
Vue.component(FormItem.name, FormItem);
Vue.component(Input.name, Input);
Vue.component(Img.name, Img);
Vue.component(Link.name, Link);
Vue.component(Radio.name, Radio);
Vue.component(RadioGroup.name, RadioGroup);
Vue.component(SideMenu.name, SideMenu);
```

### 国际化

```
import MsUi from "@shawbs/ms-ui";
import "@shawbs/ms-ui/lib/theme/index.css";
import en from "@shawbs/ms-ui/lib/locale/lang/en";

Vue.use(MsUi, { locale: en });
```

### 主题化

```
import MsUi from "@shawbs/ms-ui";
import "./ms-ui.scss";
Vue.use(MsUi);
```
ms-ui.scss
```
/* 改变主题色变量 */
$--color-primary: teal;

/* 改变 icon 字体路径变量，必需 */
$--font-path: '~@shawbs/ms-ui/lib/theme/font';

@import "~@shawbs/ms-ui/src/main/packages/theme/src/index";
```

## 组件

### button
```vue
<h3>button</h3>
<ms-button is-block>default</ms-button>
<ms-button type="primary">primary</ms-button>
<ms-button type="success">success</ms-button>
<ms-button type="danger">danger</ms-button>
<h3>轮廓</h3>
    <ms-button type="primary" outline>primary</ms-button>
    <ms-button type="success" outline>success</ms-button>
    <ms-button type="danger" outline>danger</ms-button>
<h3>禁用</h3>
<ms-button type="danger" disabled>danger</ms-button>
<ms-button type="primary" disabled>primary</ms-button>
<ms-button disabled>default</ms-button>
<h3>大小： small, medium, large</h3>
<ms-button size="small">small</ms-button>
<ms-button size="medium">medium</ms-button>
<ms-button size="large">large</ms-button>
<h3>带图标</h3>
<ms-button loading>loading</ms-button>
<h3>按钮组</h3>
<ms-button-group>
    <ms-button type="primary" icon="loading">primary</ms-button>
    <ms-button type="success" icon="close">success</ms-button>
    <ms-button type="danger" icon="tip"></ms-button>
    <ms-button type="danger" icon="tip" disabled></ms-button>
    <ms-button type="primary" icon="loading" disabled>primary</ms-button>
</ms-button-group>
```


### from
```vue
<ms-form ref="form" :model="formData" :rules="rules" label-width="100px">
    <ms-form-item label="username" prop="username">
    <ms-input v-model="formData.username"></ms-input>
    </ms-form-item>
    <ms-form-item label="phone" prop="phone">
    <ms-input v-model="formData.phone"></ms-input>
    </ms-form-item>
    <ms-form-item label="介绍">
        <ms-input type="textarea" placeholder="asda" v-model="formData.introduction"></ms-input>
    </ms-form-item>
    <ms-form-item label="">
    <ms-button type="primary" @click.native="submit">submit</ms-button>
    <ms-button @click.native="clear">clear</ms-button>
    </ms-form-item>
</ms-form>
```
| prop        | 类型           | 说明  |
| ------------- |:-------------:| -----:|
| model      | Object |  表单数据map|
| rules      | Object |  校验规则，和model中的属性对应

form-item

| prop        | 类型           | 说明  |
| ------------- |:-------------:| -----:|
| prop      | String | 对应model中的属性|

### input

```vue
<ms-input v-model="inputValue">
    <ms-icon icon="loading" slot="prepend"></ms-icon>
    <ms-icon icon="loading" slot="prefix"></ms-icon>
    <ms-icon icon="loading" slot="suffix"></ms-icon>
    <ms-icon icon="loading" slot="append"></ms-icon>
</ms-input>
<ms-input v-model="inputValue" show-close></ms-input>
<ms-input type="textarea" placeholder="asda" v-model="inputValue"></ms-input>
```

### radio
```vue
<ms-radio v-model="radioValue" label="1">aaa</ms-radio>
<ms-radio v-model="radioValue" label="2">bbb</ms-radio>
<ms-radio v-model="radioValue" label="3">ccc</ms-radio>
<ms-radio v-model="radioValue" label="4" disabled>ccc</ms-radio>
<br>
<ms-radio-group v-model="radioValue">
    <ms-radio label="1">aaa</ms-radio>
    <ms-radio label="2">bbb</ms-radio>
</ms-radio-group>
```

### checkbox
```vue
<ms-checkbox v-model="agree" >ccc</ms-checkbox>
<ms-checkbox v-model="agree" disabled>ccc</ms-checkbox>
<br>
<ms-checkbox-group v-model="checkbox">
    <ms-checkbox label="1">你的</ms-checkbox>
    <ms-checkbox label="2">我的</ms-checkbox>
</ms-checkbox-group>
```
| prop        | 类型           | 说明  |
| ------------- |:-------------:| -----:|
| value      | Boolean,Array |  |

### layout
```vue
<ms-page>
    <ms-header>header</ms-header>
    <ms-container>container</ms-container>
    <ms-footer>footer</ms-footer>
</ms-page>
```
### img
```vue
fill
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria.jpg" fit="fill" :width="width" :height="height"></ms-img>
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria123.jpg" fit="fill" :width="width" :height="height"></ms-img>
<br/>
contain
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria.jpg" fit="contain" :width="width" :height="height"></ms-img>
<br/>
cover
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria.jpg" fit="cover" :width="width" :height="height"></ms-img>
<br/>
none
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria.jpg" fit="none" :width="width" :height="height"></ms-img>
<br/>
scale-down
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria.jpg" fit="scale-down" :width="width" :height="height"></ms-img>
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria.jpg" fit="fill" :width="width" :height="height"></ms-img>
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria123.jpg" fit="fill" :width="width" :height="height">
    <span slot="error">加载失败</span>
</ms-img>
<br/>
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria.jpg" fit="fill" :width="width" :height="height"></ms-img>
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria123.jpg" fit="fill" :width="width" :height="height"></ms-img>
<br/>
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria.jpg" fit="fill" :width="width" :height="height"></ms-img>
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria123.jpg" fit="fill" :width="width" :height="height"></ms-img>
<br/>

<ms-img src="https://fuss10.elemecdn.com/9/bb/e27858e973f5d7d3904835f46abbdjpeg.jpeg" fit="scale-down" :width="width" :height="height" lazy></ms-img>
<ms-img src="https://fuss10.elemecdn.com/d/e6/c4d93a3805b3ce3f323f7974e6f78jpeg.jpeg" fit="scale-down" :width="width" :height="height" lazy></ms-img>
<ms-img src="https://interactive-examples.mdn.mozilla.net/media/examples/plumeria.jpg" fit="scale-down" :width="width" :height="height" lazy></ms-img>
        
```

### icon
```vue
<ms-icon icon="home"></ms-icon>
```

### link
```vue
<ms-link href="#/other"> link other page</ms-link>
<ms-link href="#/other" type="danger"> link other page</ms-link>
<ms-link href="#/other" type="primary"> link other page</ms-link>
<ms-link href="#/other" type="primary" disabled> link other page</ms-link>
<ms-link href="#/other" disabled> link other page</ms-link>
```

### tabbar
```vue
<ms-tabbar v-model="tabbarName" position="top">
    <ms-tabbar-item name="1">top</ms-tabbar-item>
    <ms-tabbar-item name="2">top</ms-tabbar-item>
    <ms-tabbar-item name="3">top</ms-tabbar-item>
</ms-tabbar>
<h3 v-for="item in 10" :key="item">{{item}}</h3>
<ms-tabbar v-model="tabbarName">
    <ms-tabbar-item name="1">item</ms-tabbar-item>
    <ms-tabbar-item name="2">item</ms-tabbar-item>
    <ms-tabbar-item name="3">item</ms-tabbar-item>
</ms-tabbar>

<ms-tabbar v-model="tabbarName" position="bottom">
    <ms-tabbar-item name="1">bottom</ms-tabbar-item>
    <ms-tabbar-item name="2">bottom</ms-tabbar-item>
    <ms-tabbar-item name="3">bottom</ms-tabbar-item>
</ms-tabbar>
```
### cell
```vue

<ms-cell-group title="cell1">
    <ms-cell label="asd" link>
        <div slot="suffix">asd</div>
    </ms-cell>
    <ms-cell label="asd" link>
        <ms-input></ms-input>
        <div slot="suffix"><ms-icon icon="home"></ms-icon></div>
    </ms-cell>
    <ms-cell>asd

        <div slot="suffix"><ms-icon icon="home"></ms-icon></div>
    </ms-cell>
</ms-cell-group>
<ms-cell-group style="margin-top: 20px;">
    <ms-cell label="asd" link>
        <div slot="suffix">asd</div>
    </ms-cell>
    <ms-cell label="asd" link>
        <ms-input></ms-input>
        <div slot="suffix"><ms-icon icon="home"></ms-icon></div>
    </ms-cell>
    <ms-cell>asd

        <div slot="suffix"><ms-icon icon="home"></ms-icon></div>
    </ms-cell>
</ms-cell-group>
```

### loading

```vue
<ms-button
    @click.native="$loading.show('加载中', { isClickOtherClose: true })"
    >带文字</ms-button
>
<ms-button @click.native="$loading.show('', { isClickOtherClose: true })"
    >不带文字</ms-button
>
```

### toast

```vue
<ms-button @click.native="$toast('asdasdasd')">center</ms-button>
<ms-button @click.native="$toast('asdasdasd', {align: 'top'})">top</ms-button>.
<ms-button @click.native="$toast('asdasdasd',{align: 'bottom'})">bottom</ms-button>
```

### message-box
```vue
<ms-button @click.native="$msgbox.alert('alert',{title: '标题'})">alert</ms-button>
<ms-button @click.native="$msgbox.alert('alert', {isClickOtherClose: false})">不允许点击蒙层关闭</ms-button>
<ms-button @click.native="$msgbox.confirm('confirm',{title: '标题'})">confirm</ms-button>
<ms-button @click.native="$msgbox.prompt('prompt',{title: '标题'})">prompt</ms-button>
<ms-button @click.native="beforeClose">before close handle</ms-button>


...
    methods: {
        beforeClose(){
            this.$msgbox.prompt(
                'prompt',
                {
                    title: '标题',
                    beforeClose: _ => {
                        return new Promise((resolve, reject)=>{
                            console.log('before close')
                            setTimeout(() => {
                                resolve()
                            }, 3000);
                        })
                    }
                })
        }
    }
```


### drawer
```vue
<ms-button block @click.native="action('ltr')" type="primary">从左边出来</ms-button>
<ms-button block @click.native="action('rtl')" type="primary">从右边出来</ms-button>
<ms-button block @click.native="action('ttb')" type="primary">从上边出来</ms-button>
<ms-button block @click.native="action('btt')" type="primary">从下边出来</ms-button>
<ms-drawer :direction="direction" v-model="visible">
    {{direction}}
</ms-drawer>
```

### sidemenu

```vue
<ms-side-menu>
    <div>
        left
    </div>
</ms-side-menu>


<ms-side-menu position="right">
    <div>
        right
    </div>
</ms-side-menu>
```