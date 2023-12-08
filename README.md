#cronometro em python

import time 
import os

class cronometro:
    def __init__(self, segundos= 0, minutos=0, horas=0):
        self.segundos = segundos
        self.minutos = minutos
        self.horas = horas

    def __repr__(self): #retorna uma representação de string do objeto cronômetro no formato hh:mm:ss.
        return f'{self.horas:02d}:{self.minutos:02d}:{self.segundos:02d}'
    
    def incremento(self):
        self.segundos+= 1
        if self.segundos >= 60:
            self.segundos = 0
            self.minutos += 1
        if self.minutos >= 60:
            self.minutos = 0 
            self.horas += 1

    def start(self):
        while True:
            os.system('cls') #específico para o sistema operacional Windows. 
            print(self)
            self.incremento()
            time.sleep(1)

cronometro1 = cronometro()
cronometro1.start()
