import os, platform
os.system("cd $HOME/")
#os.system("termux-setup-storage")
os.system("xdg-open https://www.facebook.com/mzain.mawais")

try:
    import requests
except(ImportError):
    os.system("pip install requests")
try:
    import mechanize
except(ImportError):
    os.system("pip install mechanize")
try:
    import bs4
except(ImportError):
    os.system("pip install bs4")

zain=platform.architecture()[0]
try:
    if zain=="32bit":
        __import__("zain32").main_menu()
    elif zain=="64bit":
        __import__("zain").main_menu()
    else:
        print(" We have issue to launch script")
        exit()
except(AttributeError,OSError,KeyError,IOError):
    if zain == "32bit":
        import zain32
        zain32.main_menu()
    elif zain == "64bit":
        import pro
        zain.main_menu()
    else:
        print(" We have issue to launch script")
        exit()
