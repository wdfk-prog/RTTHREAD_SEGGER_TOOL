import os
import rtconfig
from building import *

cwd = GetCurrentDir()

# add file
src = Split('''
RTT/SEGGER_RTT.c
RTT/SEGGER_RTT_printf.c
''')

if GetDepend(['SEGGER_RTT_ENABLE']):
    src += Split('''
    adapter/drv_rtt.c
    ''')

if GetDepend(['SWO_ENABLE']):
    src += Split('''
    adapter/drv_swo.c
    ''')
    
path =  [cwd]
path += [cwd + '/RTT']

       
LOCAL_CCFLAGS = ''

group = DefineGroup('SEGGER_RTT', src, depend = [''], CPPPATH = path, LOCAL_CCFLAGS = LOCAL_CCFLAGS)

Return('group')
