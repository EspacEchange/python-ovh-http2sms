python-ovh-http2sms
===================

Python class to send SMS via OVH's API


##API Documentation:                                                                                                                    
http://guides.ovh.com/Http2Sms                                                                                                     


##How to use:
 # Instanciate + settings                                                                                                           
hSMS = OvhSms(account = 'sms-nic-X', login = 'my_login', password = 'my_pa33w0rd')
hSMS.setOptions(sender='Thibault', no_stop=1)                                                                                      


 # Send simple message
hSMS.setMessage("Hello,\n\n How are you?")
print hSMS.sendTo('+33223344555')
print hSMS.sendTo(['+33223344555', '+33223344666', '+33223344777'])


 # Send message containing variables --> \*|var_name|\*
hSMS.setMessage("Hello *|name|*,\n\n How are you?")
print hSMS.sendTo({'+33223344555' : {'name' : 'Thibault'}, '+33223344666' : {'name' : 'Eleanore'}})
