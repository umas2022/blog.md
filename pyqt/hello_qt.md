# hello qt
python+QT 项目基本操作

## hello world
- 使用pyqt创建一个简单的单窗口页面
- 项目位置: 1_example/pyqt
### 1. 一个简单的窗口  
```python
import sys

from PyQt6.QtCore import QSize
from PyQt6.QtWidgets import QApplication, QMainWindow, QPushButton

class MainWindow(QMainWindow):
    def __init__(self):
        super().__init__()

        self.setWindowTitle("hello world")
        button = QPushButton("Press Me!")

        self.setFixedSize(QSize(800, 600))
        self.setCentralWidget(button)

app = QApplication(sys.argv)
window = MainWindow()
window.show()
# Start the event loop.
app.exec()
```

### 2. 项目打包
- 打包使用pyinstaller工具,需要先安装
```
pip install pyinstaller
pyinstaller.exe -F -w .\window.py
```
- 打包参数