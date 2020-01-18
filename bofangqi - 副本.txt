# Code By Wulongxiang

from PyQt5 import QtCore, QtGui, QtWidgets

import sys
import qtawesome


class MainUi(QtWidgets.QMainWindow):
    def __init__(self):
        super().__init__()
        self.init_ui()

    # 一、对界面进行布局和组件的布置
    # 在图像界面编程中，一个好的布局有助于全局把控界面的形态，而在PyQt5中，有多种布局的方式供我们选择，比较常用的布局有以下几种：
    # 表单布局：QFormLayout
    # 网格布局：QGridLayout
    # 水平排列布局：QHBoxLayout
    # 垂直排列布局：QVBoxLayout
    def init_ui(self):
        self.setFixedSize(960, 700)
        self.main_widget = QtWidgets.QWidget()  # 创建窗口主部件
        self.main_layout = QtWidgets.QGridLayout()  # 创建主部件的网格布局
        self.main_widget.setLayout(self.main_layout)  # 设置窗口主部件布局为网格布局
        self.left_widget = QtWidgets.QWidget()  # 创建左侧部件
        self.left_widget.setObjectName('left_widget')
        self.left_layout = QtWidgets.QGridLayout()  # 创建左侧部件的网格布局层
        self.left_widget.setLayout(self.left_layout)  # 设置左侧部件布局为网格
        self.right_widget = QtWidgets.QWidget()  # 创建右侧部件
        self.right_widget.setObjectName('right_widget')
        self.right_layout = QtWidgets.QGridLayout()
        self.right_widget.setLayout(self.right_layout)  # 设置右侧部件布局为网格
        self.main_layout.addWidget(self.left_widget, 0, 0, 12, 2)  # 左侧部件在第0行第0列，占8行3列
        self.main_layout.addWidget(self.right_widget, 0, 2, 12, 10)  # 右侧部件在第0行第3列，占8行9列
        self.setCentralWidget(self.main_widget)  # 设置窗口主部件

        self.left_close = QtWidgets.QPushButton("")  # 关闭按钮
        self.left_visit = QtWidgets.QPushButton("")  # 空白按钮
        self.left_mini = QtWidgets.QPushButton("")  # 最小化按钮
        self.left_label_1 = QtWidgets.QPushButton("每日推荐")
        self.left_label_1.setObjectName('left_label')
        self.left_label_2 = QtWidgets.QPushButton("我的音乐")


        self.left_label_2.setObjectName('left_label')
        self.left_label_3 = QtWidgets.QPushButton("联系与帮助")
        self.left_label_3.setObjectName('left_label')
        self.left_button_1 = QtWidgets.QPushButton(qtawesome.icon('fa.music', color='white'), "华语流行")
        self.left_button_1.setObjectName('left_button')
        self.left_button_2 = QtWidgets.QPushButton(qtawesome.icon('fa.sellsy', color='white'), "在线FM")
        self.left_button_2.setObjectName('left_button')
        self.left_button_3 = QtWidgets.QPushButton(qtawesome.icon('fa.film', color='white'), "热门MV")
        self.left_button_3.setObjectName('left_button')
        self.left_button_4 = QtWidgets.QPushButton(qtawesome.icon('fa.home', color='white'), "本地音乐")
        self.left_button_4.setObjectName('left_button')
        self.left_button_5 = QtWidgets.QPushButton(qtawesome.icon('fa.download', color='white'), "下载管理")
        self.left_button_5.setObjectName('left_button')
        self.left_button_6 = QtWidgets.QPushButton(qtawesome.icon('fa.heart', color='white'), "我的收藏")
        self.left_button_6.setObjectName('left_button')
        self.left_button_7 = QtWidgets.QPushButton(qtawesome.icon('fa.comment', color='white'), "反馈建议")
        self.left_button_7.setObjectName('left_button')
        self.left_button_8 = QtWidgets.QPushButton(qtawesome.icon('fa.star', color='white'), "关注我们")
        self.left_button_8.setObjectName('left_button')
        self.left_button_9 = QtWidgets.QPushButton(qtawesome.icon('fa.question', color='white'), "遇到问题")
        self.left_button_9.setObjectName('left_button')
        self.left_xxx = QtWidgets.QPushButton(" ")
        # 我们使用qtawesome这个第三方库来实现按钮中的Font Awesome字体图标的显示。然后将创建的按钮添加到左侧部件的网格布局层中
        self.left_layout.addWidget(self.left_mini, 0, 0, 1, 1)
        self.left_layout.addWidget(self.left_close, 0, 2, 1, 1)
        self.left_layout.addWidget(self.left_visit, 0, 1, 1, 1)
        self.left_layout.addWidget(self.left_label_1, 1, 0, 1, 3)
        self.left_layout.addWidget(self.left_button_1, 2, 0, 1, 3)
        self.left_layout.addWidget(self.left_button_2, 3, 0, 1, 3)
        self.left_layout.addWidget(self.left_button_3, 4, 0, 1, 3)
        self.left_layout.addWidget(self.left_label_2, 5, 0, 1, 3)
        self.left_layout.addWidget(self.left_button_4, 6, 0, 1, 3)
        self.left_layout.addWidget(self.left_button_5, 7, 0, 1, 3)
        self.left_layout.addWidget(self.left_button_6, 8, 0, 1, 3)
        self.left_layout.addWidget(self.left_label_3, 9, 0, 1, 3)
        self.left_layout.addWidget(self.left_button_7, 10, 0, 1, 3)
        self.left_layout.addWidget(self.left_button_8, 11, 0, 1, 3)
        self.left_layout.addWidget(self.left_button_9, 12, 0, 1, 3)
        # 在右侧内容模块中，有以下几个主要内容模块：
        # 搜索模块
        # 推荐音乐模块
        # 音乐列表模块
        # 音乐歌单模块
        # 音乐播放进度模块
        # 音乐播放控制模块
        # 在搜索模块中，有一个文本和一个搜索框，我们通过QLable()部件和QLineEdit()部件来实现，
        # 这两个部件同时包裹在一个网格布局的QWidget()部件，分列第一列和第二列，其代码如下所示
        self.right_bar_widget = QtWidgets.QWidget()  # 右侧顶部搜索框部件
        self.right_bar_layout = QtWidgets.QGridLayout()  # 右侧顶部搜索框网格布局
        self.right_bar_widget.setLayout(self.right_bar_layout)
        self.search_icon = QtWidgets.QLabel(chr(0xf002) + ' ' + '搜索 ')
        self.search_icon.setFont(qtawesome.font('fa', 16))
        self.right_bar_widget_search_input = QtWidgets.QLineEdit()
        self.right_bar_widget_search_input.setPlaceholderText("输入歌手、歌曲或用户，回车进行搜索")
        self.right_bar_layout.addWidget(self.search_icon, 0, 0, 1, 1)
        self.right_bar_layout.addWidget(self.right_bar_widget_search_input, 0, 1, 1, 8)
        self.right_layout.addWidget(self.right_bar_widget, 0, 0, 1, 9)
        # 然后是推荐音乐模块，在推荐音乐模块中，有一个推荐的标题，和一个横向排列的音乐封面列表，在这里：
        # 推荐标题使用QLable()来实现
        # 音乐封面列表由多个QToolButton()组成，其继续由一个布局为QGridLayout()的QWidget()部件所包含。
        self.right_recommend_label = QtWidgets.QLabel("今日推荐")
        self.right_recommend_label.setObjectName('right_lable')
        self.right_recommend_widget = QtWidgets.QWidget()  # 推荐封面部件
        self.right_recommend_layout = QtWidgets.QGridLayout()  # 推荐封面网格布局
        self.right_recommend_widget.setLayout(self.right_recommend_layout)
        self.recommend_button_1 = QtWidgets.QToolButton()
        self.recommend_button_1.setText("可馨HANM")  # 设置按钮文本
        self.recommend_button_1.setIcon(QtGui.QIcon('./r1.jpg'))  # 设置按钮图标
        self.recommend_button_1.setIconSize(QtCore.QSize(100, 100))  # 设置图标大小
        self.recommend_button_1.setToolButtonStyle(QtCore.Qt.ToolButtonTextUnderIcon)  # 设置按钮形式为上图下文
        self.recommend_button_2 = QtWidgets.QToolButton()
        self.recommend_button_2.setText("那首歌")
        self.recommend_button_2.setIcon(QtGui.QIcon('./r2.jpg'))
        self.recommend_button_2.setIconSize(QtCore.QSize(100, 100))
        self.recommend_button_2.setToolButtonStyle(QtCore.Qt.ToolButtonTextUnderIcon)
        self.recommend_button_3 = QtWidgets.QToolButton()
        self.recommend_button_3.setText("伟大的渺小")
        self.recommend_button_3.setIcon(QtGui.QIcon('./r3.jpg'))
        self.recommend_button_3.setIconSize(QtCore.QSize(100, 100))
        self.recommend_button_3.setToolButtonStyle(QtCore.Qt.ToolButtonTextUnderIcon)
        self.recommend_button_4 = QtWidgets.QToolButton()
        self.recommend_button_4.setText("荣耀征战")
        self.recommend_button_4.setIcon(QtGui.QIcon('./r4.jpg'))
        self.recommend_button_4.setIconSize(QtCore.QSize(100, 100))
        self.recommend_button_4.setToolButtonStyle(QtCore.Qt.ToolButtonTextUnderIcon)
        self.recommend_button_5 = QtWidgets.QToolButton()
        self.recommend_button_5.setText("猎场合辑")
        self.recommend_button_5.setIcon(QtGui.QIcon('./r5.jpg'))
        self.recommend_button_5.setIconSize(QtCore.QSize(100, 100))
        self.recommend_button_5.setToolButtonStyle(QtCore.Qt.ToolButtonTextUnderIcon)
        self.right_recommend_layout.addWidget(self.recommend_button_1, 0, 0)
        self.right_recommend_layout.addWidget(self.recommend_button_2, 0, 1)
        self.right_recommend_layout.addWidget(self.recommend_button_3, 0, 2)
        self.right_recommend_layout.addWidget(self.recommend_button_4, 0, 3)
        self.right_recommend_layout.addWidget(self.recommend_button_5, 0, 4)
        self.right_layout.addWidget(self.right_recommend_label, 1, 0, 1, 9)
        self.right_layout.addWidget(self.right_recommend_widget, 2, 0, 2, 9)
        # 接着创建音乐列表模块和音乐歌单模块。音乐列表模块和音乐歌单模块都有一个标题和一个小部件来容纳具体的内容。
        # 其中标题我们都使用QLabel()部件来实现，而音乐列表我们使用网格布局的QWidget()部件下包裹着数个QPushButton()
        # 按钮部件来实现，音乐歌单列表则使用网格布局的QWidget()部件下包裹着数个QToolButton()工具按钮部件来实现。
        # 音乐列表的具体代码如下所示：
        self.right_newsong_lable = QtWidgets.QLabel("最新歌曲")
        self.right_newsong_lable.setObjectName('right_lable')
        self.right_playlist_lable = QtWidgets.QLabel("热门歌单")
        self.right_playlist_lable.setObjectName('right_lable')
        self.right_newsong_widget = QtWidgets.QWidget()  # 最新歌曲部件
        self.right_newsong_layout = QtWidgets.QGridLayout()  # 最新歌曲部件网格布局
        self.right_newsong_widget.setLayout(self.right_newsong_layout)
        self.newsong_button_1 = QtWidgets.QPushButton("夜机 陈慧娴 永远的朋友 03::29")
        self.newsong_button_2 = QtWidgets.QPushButton("夜机 陈慧娴 永远的朋友 03::29")
        self.newsong_button_3 = QtWidgets.QPushButton("夜机 陈慧娴 永远的朋友 03::29")
        self.newsong_button_4 = QtWidgets.QPushButton("夜机 陈慧娴 永远的朋友 03::29")
        self.newsong_button_5 = QtWidgets.QPushButton("夜机 陈慧娴 永远的朋友 03::29")
        self.newsong_button_6 = QtWidgets.QPushButton("夜机 陈慧娴 永远的朋友 03::29")
        self.right_newsong_layout.addWidget(self.newsong_button_1, 0, 1, )
        self.right_newsong_layout.addWidget(self.newsong_button_2, 1, 1, )
        self.right_newsong_layout.addWidget(self.newsong_button_3, 2, 1, )
        self.right_newsong_layout.addWidget(self.newsong_button_4, 3, 1, )
        self.right_newsong_layout.addWidget(self.newsong_button_5, 4, 1, )
        self.right_newsong_layout.addWidget(self.newsong_button_6, 5, 1, )
        # 音乐歌单模块的代码如下所示：
        self.right_playlist_widget = QtWidgets.QWidget()  # 播放歌单部件
        self.right_playlist_layout = QtWidgets.QGridLayout()  # 播放歌单网格布局
        self.right_playlist_widget.setLayout(self.right_playlist_layout)
        self.playlist_button_1 = QtWidgets.QToolButton()
        self.playlist_button_1.setText("无法释怀的整天循环音乐…")
        self.playlist_button_1.setIcon(QtGui.QIcon('./p1.jpg'))
        self.playlist_button_1.setIconSize(QtCore.QSize(100, 100))
        self.playlist_button_1.setToolButtonStyle(QtCore.Qt.ToolButtonTextUnderIcon)
        self.playlist_button_2 = QtWidgets.QToolButton()
        self.playlist_button_2.setText("不需要歌词,也可以打动你的心")
        self.playlist_button_2.setIcon(QtGui.QIcon('./p2.jpg'))
        self.playlist_button_2.setIconSize(QtCore.QSize(100, 100))
        self.playlist_button_2.setToolButtonStyle(QtCore.Qt.ToolButtonTextUnderIcon)
        self.playlist_button_3 = QtWidgets.QToolButton()
        self.playlist_button_3.setText("那些你熟悉又不知道名字…")
        self.playlist_button_3.setIcon(QtGui.QIcon('./p3.jpg'))
        self.playlist_button_3.setIconSize(QtCore.QSize(100, 100))
        self.playlist_button_3.setToolButtonStyle(QtCore.Qt.ToolButtonTextUnderIcon)
        self.playlist_button_4 = QtWidgets.QToolButton()
        self.playlist_button_4.setText("那些只听前奏就中毒的英文歌")
        self.playlist_button_4.setIcon(QtGui.QIcon('./p4.jpg'))
        self.playlist_button_4.setIconSize(QtCore.QSize(100, 100))
        self.playlist_button_4.setToolButtonStyle(QtCore.Qt.ToolButtonTextUnderIcon)
        self.right_playlist_layout.addWidget(self.playlist_button_1, 0, 0)
        self.right_playlist_layout.addWidget(self.playlist_button_2, 0, 1)
        self.right_playlist_layout.addWidget(self.playlist_button_3, 1, 0)
        self.right_playlist_layout.addWidget(self.playlist_button_4, 1, 1)
        # 然后将它们添加到右侧布局层中：
        self.right_layout.addWidget(self.right_newsong_lable, 4, 0, 1, 5)
        self.right_layout.addWidget(self.right_playlist_lable, 4, 5, 1, 4)
        self.right_layout.addWidget(self.right_newsong_widget, 5, 0, 1, 5)
        self.right_layout.addWidget(self.right_playlist_widget, 5, 5, 1, 4)
        # 基本上能够看得出来图形界面的模样了，还差最后的音乐播放进度条和音乐播放控制按钮组。
        # 音乐播放进度条我们使用QProgressBar()进度条部件来实现，音乐播放控制按钮组则使用一个QWidget()部件下包裹着三个QPushButton()
        # 按钮部件来实现。
        # =其具体代码如下
        self.right_process_bar = QtWidgets.QProgressBar()  # 播放进度部件
        self.right_process_bar.setValue(49)
        self.right_process_bar.setFixedHeight(3)  # 设置进度条高度
        self.right_process_bar.setTextVisible(False)  # 不显示进度条文字
        self.right_playconsole_widget = QtWidgets.QWidget()  # 播放控制部件
        self.right_playconsole_layout = QtWidgets.QGridLayout()  # 播放控制部件网格布局层
        self.right_playconsole_widget.setLayout(self.right_playconsole_layout)
        self.console_button_1 = QtWidgets.QPushButton(qtawesome.icon('fa.backward', color='#F76677'), "")
        self.console_button_2 = QtWidgets.QPushButton(qtawesome.icon('fa.forward', color='#F76677'), "")
        self.console_button_3 = QtWidgets.QPushButton(qtawesome.icon('fa.pause', color='#F76677', font=18), "")
        self.console_button_3.setIconSize(QtCore.QSize(30, 30))
        self.right_playconsole_layout.addWidget(self.console_button_1, 0, 0)
        self.right_playconsole_layout.addWidget(self.console_button_2, 0, 2)
        self.right_playconsole_layout.addWidget(self.console_button_3, 0, 1)
        self.right_playconsole_layout.setAlignment(QtCore.Qt.AlignCenter)  # 设置布局内部件居中显示
        self.right_layout.addWidget(self.right_process_bar, 9, 0, 1, 9)
        self.right_layout.addWidget(self.right_playconsole_widget, 10, 0, 1, 9)



        # 二、使用QSS和部件属性美化窗口部件
        # QSS全称为Qt StyleSheet,是用来控制QT控件的样式表。其和Web前段开发中的CSS样式表类似，
        # 接下来，我们就通过QSS来对上面创建好的图形界面进行美化。
        # 窗口控制按钮首先从左侧的菜单栏开始。左侧的最顶端是三个窗口控制按钮，我们需要将其设置为小圆点的形式。
        # 首先，我们使用QPushButton()的setFixedSize()方法，设置按钮的大小：

        self.left_close.setFixedSize(15, 15)  # 设置关闭按钮的大小
        self.left_visit.setFixedSize(15, 15)  # 设置按钮大小
        self.left_mini.setFixedSize(15, 15)  # 设置最小化按钮大小

        # 然后，通过setStyleSheet()方法，设置按钮部件的QSS样式，在这里，左侧按钮默认为淡绿色，
        # 鼠标悬浮时为深绿色；中间按钮默认为淡黄色，鼠标悬浮时为深黄色；右侧按钮默认为浅红色，鼠标悬浮时为红色。
        # 所以它们的QSS样式设置如下所示：

        self.left_close.setStyleSheet(
            '''QPushButton{background:#F76677;border-radius:5px;}QPushButton:hover{background:red;}''')
        self.left_visit.setStyleSheet(
            '''QPushButton{background:#F7D674;border-radius:5px;}QPushButton:hover{background:yellow;}''')
        self.left_mini.setStyleSheet(
            '''QPushButton{background:#6DDF6D;border-radius:5px;}QPushButton:hover{background:green;}''')

        # 左侧菜单按钮
        # 因为最后的图形界面中，左侧的部件背景是灰色的，所以我们需要将左侧菜单中的按钮和文字颜色设置为白色，
        # 并且将按钮的边框去掉，在left_widget中设置qss样式为：
        # 为了避免隐藏窗口边框后，左侧部件没有背景颜色和边框显示，我们再对左侧部件添加QSS属性：
        self.left_widget.setStyleSheet('''
                QPushButton{border:none;color:white;}
                QPushButton#left_label{
                border:none;
                border-bottom:1px solid white;
                font-size:18px;
                font-weight:700;
                font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
                }
                                
                QPushButton#left_button:hover{border-left:4px solid red;font-weight:700;}
         
                QWidget#left_widget{
                background:gray;
                border-top:1px solid white;
                border-bottom:1px solid white;
                border-left:1px solid white;
                border-top-left-radius:10px;
                border-bottom-left-radius:10px;
                }
                ''')

        # 右侧背景、搜索框和模块文本
        # 完成了左侧部件的美化之后，我们接着对右侧的内容部件进行处理，首先是顶部的搜索框，
        # 因为搜索框使用的是QLineEdit()部件，默认情况下棱角分明很是不好看，我们对其进行圆角处理：

        self.right_bar_widget_search_input.setStyleSheet(
                '''QLineEdit{
                border:1px solid gray;
                width:300px;
                border-radius:10px;
                padding:2px 4px;
                }''')

        # 因为图形界面是会呈现出无边框的圆角形式，所以右侧的部件的右上角和右下角需要先行处理为圆角的，
        # 同时背景设置为白色。对推荐模块、音乐列表模块和音乐歌单模块的标题我们也需要对其字体进行放大处理，所以最后的样式为：

        self.right_widget.setStyleSheet('''
                QWidget#right_widget{
                color:#232C51;
                background:white;
                border-top:1px solid darkGray;
                border-bottom:1px solid darkGray;
                border-right:1px solid darkGray;
                border-top-right-radius:10px;
                border-bottom-right-radius:10px;
                }
                QLabel#right_lable{
                border:none;
                font-size:16px;
                font-weight:700;
                font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
                }
                ''')

        # 推荐模块、歌单模块和歌曲列表模块
        # 因为推荐模块和歌单模块中使用的都是QToolButton()
        # 部件，所以其样式也类似：

        self.right_recommend_widget.setStyleSheet(
                '''
                 QToolButton{border:none;}
                 QToolButton:hover{border-bottom:2px solid #F76677;}
                 ''')
        self.right_playlist_widget.setStyleSheet(
                '''
                 QToolButton{border:none;}
                 QToolButton:hover{border-bottom:2px solid #F76677;}
                 ''')

        # 而音乐列表使用的是QPushButton()
        # 按钮部件，我们需要对其去除边框，修改字体和颜色等，所以其样式为：

        self.right_newsong_widget.setStyleSheet('''
                 QPushButton{
                 border:none;
                 color:gray;
                 font-size:12px;
                 height:40px;
                 padding-left:5px;
                 padding-right:10px;
                 text-align:left;
                 }
                 QPushButton:hover{
                 color:black;
                 border:1px solid #F3F3F5;
                 border-radius:10px;
                 background:LightGray;
                 }
                 ''')

        # 播放进度条和播放控制按钮组
        # 接下来轮到播放进度条和播放控制按钮组了，我们需要将播放进度条的样色设置为浅红色，
        # 然后去除播放控制按钮的边框，所以其QSS样式为：

        self.right_process_bar.setStyleSheet('''
                 QProgressBar::chunk {
                 background-color: #F76677;
                 }
                 ''')
        self.right_playconsole_widget.setStyleSheet('''
                 QPushButton{
                 border:none;
                 }
                 ''')

        # 设置窗口背景透明
        # 透明的窗口背景会让图形界面有现代感和时尚感，我们来讲图形界面的窗口背景设为透明：

        self.setWindowOpacity(0.9)  # 设置窗口透明度
        self.setAttribute(QtCore.Qt.WA_TranslucentBackground)  # 设置窗口背景透明

        # 去除窗口边框
        # 窗口背景设置为透明后的体验很不一样，但是那个默认的边框很不协调，那么去除丑丑的默认边框是必须要做的工作，通过窗口的setWindowFlag()
        # 属性我们可以设置窗口的状态从而把边框给隐藏了：

        self.setWindowFlag(QtCore.Qt.FramelessWindowHint)  # 隐藏边框

        self.main_layout.setSpacing(0)


def main():
    app = QtWidgets.QApplication(sys.argv)
    gui = MainUi()
    gui.show()
    sys.exit(app.exec_())


if __name__ == '__main__':
    main()
