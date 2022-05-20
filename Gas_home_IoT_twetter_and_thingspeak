import paho.mqtt.publish as publish
import sys
import RPi.GPIO as GPIO
import thingspeak
import time, os, urllib, urllib3

#Definimos los campos requeridos para la publicación en Thingspeak
channel_id = "1689185"
write_key = "4N1T3708J9L47UOH"
GAS_URL = 'https://api.thingspeak.com/apps/thingtweet/1/statuses/update?api_key=GSVUIN6PIGKH0EBJ&status=CUIDADO,GAS!'
LL_URL = 'https://api.thingspeak.com/apps/thingtweet/1/statuses/update?api_key=GSVUIN6PIGKH0EBJ&status=cuidado,lluvia'
def gasnot():
    response = urllib.request.urlopen(url=GAS_URL)
def llnot():
    response = urllib.request.urlopen(url=LL_URL)

GPIO.setmode(GPIO.BCM)
SENSOR_1_INPUT =3
GPIO.setup(SENSOR_1_INPUT, GPIO.IN)
channel=thingspeak.Channel(id=channel_id, api_key=write_key)
if _name_ == '_main_':
 while True:
  SENSOR_1_VALUE = GPIO.input(SENSOR_1_INPUT)
  print(SENSOR_1_VALUE)
  gas= SENSOR_1_VALUE
  tPayload = "&field1=" + str(gas)
  try:
    channel.update({'field1': gas})
    print("datos enviados"+tPayload)
  except:
    print("Error enviando datos")
  if gas==0:
      gasnot()
 time.sleep(3000)
