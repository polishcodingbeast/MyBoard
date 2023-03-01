# Weather app

from time import time
from tkinter import *
import requests
import json

root = Tk()
root.title('Weather app')
img = PhotoImage(file='sun.png')
root.tk.call('wm', 'iconphoto', root._w, img)  # loading icons


def zipLockup():
    try:
        api_requests = requests.get(
            'https://weather.visualcrossing.com/VisualCrossingWebServices/rest/services/timeline/' +
            choice.get()+'/today?unitGroup=metric&include=events&key=N26Y3L88WTF7GVXXUN7VK5622&contentType=json'
        )
        api = json.loads(api_requests.content)

        choice.destroy()
        zipButton.destroy()

        place = api['address']
        timezone = api['timezone']
        datetime = api['days'][0]['datetime']
        temp = api['days'][0]['temp']
        windspeed = api['days'][0]['windspeed']
        pressure = api['days'][0]['pressure']
        sunrise = api['days'][0]['sunrise']
        sunset = api['days'][0]['sunset']

        label1 = Label(root, text='Place')
        label1.grid(row=0, column=0)
        label2 = Label(root, text='Timezone')
        label2.grid(row=1, column=0)
        label3 = Label(root, text='Datetime')
        label3.grid(row=2, column=0)
        label4 = Label(root, text='Temp')
        label4.grid(row=3, column=0)
        label5 = Label(root, text='Windspeed')
        label5.grid(row=4, column=0)
        label6 = Label(root, text='Pressure')
        label6.grid(row=5, column=0)
        label7 = Label(root, text='Sunrise')
        label7.grid(row=6, column=0)
        label8 = Label(root, text='Sunset')
        label8.grid(row=7, column=0)

        labelValues1 = Label(root, text=place)
        labelValues1.grid(row=0, column=1)
        labelValues2 = Label(root, text=timezone)
        labelValues2.grid(row=1, column=1)
        labelValues3 = Label(root, text=datetime)
        labelValues3.grid(row=2, column=1)
        labelValues4 = Label(root, text=temp)
        labelValues4.grid(row=3, column=1)
        labelValues5 = Label(root, text=windspeed)
        labelValues5.grid(row=4, column=1)
        labelValues6 = Label(root, text=pressure)
        labelValues6.grid(row=5, column=1)
        labelValues7 = Label(root, text=sunrise)
        labelValues7.grid(row=6, column=1)
        labelValues8 = Label(root, text=sunset)
        labelValues8.grid(row=7, column=1)

    except:
        print('something went wrong')


choice = Entry(root)
choice.grid(row=8, columnspan=2, padx=15)

zipButton = Button(root, text='Choose Country', command=zipLockup)
zipButton.grid(row=9, columnspan=2, padx=15)

root.mainloop()
