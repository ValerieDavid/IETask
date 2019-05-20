# IETask
import pyrebase
import serial 

ser=serial.Serial('COM8', 9600)

config = {"apiKey": "AIzaSyDF4asm3o574iMInFs7BrefTYBqGZX8Uxk",
    "authDomain": "ietask.firebaseapp.com",
    "databaseURL": "https://ietask.firebaseio.com",
    "projectId": "ietask",
    "storageBucket": "ietask.appspot.com",
    "messagingSenderId": "443707352877",
    "appId": "1:443707352877:web:21705d964de7f6fb"

    
  }

firebase=pyrebase.initialize_app(config)
db=firebase.database()


while 1:
    dis=ser.readline()
    det={"Distance": str(dis)}
    db.child("UltraSonic").child("Distance").set(det)

