# servo
import RPi.GPIO as gp
gp.setmode(gp.BOARD)

spin=11

gp.setup(spin,gp.OUT)
pwm=gp.PWM(spin,50)
pwm.start(7)

while 1:
    dp=input("where do you want the servo 1-180.")
    DC=1./18.*(dp)+2
    pwm.ChangeDutyCycle(DC)

pwm.stop()
gp.cleanup()
