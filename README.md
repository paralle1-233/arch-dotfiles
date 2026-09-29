# arch-dotfiles
Arch Linux + niri环境下的桌面组件配置文件

## 仓库内容
涵盖niri配置文件，kitty主题等桌面环境美化以及组件配置文件

## 桌面效果(waybar为主的组件集合)
![mahirochan](/assets/mahiro.png "效果展示")
芝士真寻
![yuukachan](/assets/yuuka.png "效果展示")
芝士优香
## 追加: noctalia效果展示
![yuukachan](/assets/yuuka1.png "noctalia效果展示")

## 使用方法
HTTPS：
`git clone https://github.com/paralle1-233/arch-dotfiles.git`

SSH：
`git clone git@github.com:paralle1-233/arch-dotfiles.git`

将需要的配置文件复制到自己的.config/组件/ 中（如果没有自行创建相应的config文件夹）

添加完组件配置文件后自行到niri配置文件内取消注释启用/禁用想要的组件

## 注意
最好waybar和noctalia之间只选择一种，以免同时出现两个状态栏

noctalia集成了waybar大多数组件，所以优先推荐noctalia，配置也可以完全靠GUI，适合上手，
waybar的组件需要自行配置，而且拓展性有限，想极致折腾个性化桌面的话更推荐quickshell~
