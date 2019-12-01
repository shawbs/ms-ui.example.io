# ms-UI

### Referring to the element- UI implementation of a Vue mobile component library, currently contains not many components, will be added later


### [EXAMPLE]()

## Install

```
npm install @shawbs/ms-ui -S
```

### All import

```
import MsUi from "@shawbs/ms-ui";
import "@shawbs/ms-ui/lib/theme/index.css";
Vue.use(MsUi, { size: "small" });
```

### Custom import
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

### i18n

```
import MsUi from "@shawbs/ms-ui";
import "@shawbs/ms-ui/lib/theme/index.css";
import en from "@shawbs/ms-ui/lib/locale/lang/en";

Vue.use(MsUi, { locale: en });
```

### Theme

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

