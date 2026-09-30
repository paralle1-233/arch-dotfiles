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

## 优缺点

**noctalia**: 
- noctalia集成了waybar大多数组件
- GUI配置方式与toml文件相互配合，且支持
`noctalia config export > ~/.config/noctalia/config.toml`
一键将GUI配置导出为可分享文件
- 适合开盒即用的用户
- 拥有200+个plugin功能，总有适合自己的小组件
- 官方文档较为全面，完全可以边看边试效果

**waybar**: 
- waybar的组件需要自行配置
- 拓展性有限，适合在json文件里写一些小功能（如arch:`sudo pacman -Syu`之类的小脚本），无法承载功能较为复杂的组件，如果功能需求不强但是想自己写一个试试手完全可以选择waybar，在反复测试里写出让自己满意的配置~
- 想极致折腾个性化状态栏的话更推荐quickshell~

**both**: 
均支持热加载，写完保存立即生效，方便调试

## 部分组件功能介绍(alphabetical)

### cava
**音频可视化组件**
module.json
```json
  "custom/cava": {
    "exec": "sh ~/.config/waybar/cava.sh",
    "format": "{}",
    "tooltip": false,
```
[github: cava](https://github.com/karlstav/cava/)
### kitty
**个人感受最舒服响应最好的终端**
特点：
- 使用 GPU 和 SIMD 矢量 CPU 指令,实现同类最佳性能
- 采用线程渲染以实现极低延迟
- 性能权衡可以调整
- 图形,带图像和动画
- 超链接,可配置操作
[kitty官网链接](https://sw.kovidgoyal.net/kitty/)
### mako
**轻量消息守护进程(for Wayland)**
[github: mako](https://github.com/emersion/mako/)
### matugen
**主题色生成器**
matugen支持根据输入图片生成主题色，并保存在waybar的color.css文件中(waybar中只保存颜色结果，变量则储存在matugen/templates/ 中)

输入图片可以自主选择，本仓库使用`awww query`获取当前壁纸生成主题色文件并立刻刷新waybar，实现bar颜色随壁纸变化~(awww没写配置文件，所以不在仓库中)
[matugen doc](https://iniox.github.io/#matugen/installation)
### swaylock
**超时锁屏**
```bash
# 5 分钟锁屏，10 分钟熄屏，20 分钟睡眠
# swaylock -f 是前台运行 swaylock，如果不加的话后续的 timeout 命令会不生效

swayidle -w \
    timeout 300  'swaylock -f' \
    timeout 600  'niri msg action power-off-monitors' \
    resume       'niri msg action power-on-monitors' \
    timeout 1200 'systemctl suspend' \
```
### waypaper
**GUI壁纸切换器前端**
适用于 Wayland、Xorg 和 macOS 的 GUI 壁纸设置器。它可作为热门壁纸后端的前端,例如 swizebg、swww、awww、wallutils、hyprpaper、mpvpaper、gslapper、xwallpaper、feh、linux-wallpaperengine 和 macos

- 支持动态壁纸：mpvpaper
- 记忆重启前使用的壁纸
- 支持linux-wallpaperengine,可让您使用steam Wallpaper Engine中的动态壁纸
[github: waypaper](https://github.com/anufrievroman/waypaper)

