# IETask
import pyrebase

config { apiKey: "AIzaSyDF4asm3o574iMInFs7BrefTYBqGZX8Uxk",
    authDomain: "ietask.firebaseapp.com",
    databaseURL: "https://ietask.firebaseio.com",
    projectId: "ietask",
    storageBucket: "ietask.appspot.com",
    messagingSenderId: "443707352877",
    appId: "1:443707352877:web:21705d964de7f6fb"
}
def connect_firebase():
username: "ValerieDavid"
password: "vdavid2001"

    firebase = pyrebase.initialize_app(config)
    auth = firebase.auth() 
    user = auth.sign_in_with_email_and_password("ValerieDavid, "vdavid2001")
    #user['idToken']
    db = firebase.database()
    db = connect_firebase()
    det={"RegNo":"18BIS0159", "Name": "Valerie David"}
    db.child("StuData").child("Stu1").set(det, user['idToken'])
