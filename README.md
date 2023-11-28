# smartbeat
Relógio SmartBeat

@startuml
title SmartBeat
top to bottom direction

actor "Usuário com problema cardíaco" as USU1
actor "Familiar do usuário" as USU2
actor "Samu" as USU3
actor "Sistema" as CPU

rectangle SistemaSmartBeat{
  usecase "Iniciar sessão" as F1
  usecase "Apresentar suas credenciais" as F2
  usecase "Verifica se as credencias são válidas" as F3
  usecase "Monitorar batimentos cardíacos" as F4
  usecase "Receber notificação de irregularidade leve" as F5
  usecase "Confirmar bem-estar" as F6
  usecase "Receber notificação de irregularidade grave" as F7
  usecase "Notificar o familiar" as F8
  usecase "Resposta do familiar" as F9
  usecase "Acionar o SAMU" as F10
  usecase "Atender chamada do SAMU" as F11

USU1 -- F1 #blue;line:blue;line.bold;text:blue
USU1 -right- F2 #blue;line:blue;line.bold;text:blue
CPU -right- F3 #blue;line:blue;line.bold;text:blue
CPU -right- F4 #blue;line:blue;line.bold;text:blue
USU1 -right- F5 #blue;line:blue;line.bold;text:blue
USU2 <-- F6 #blue;line:blue;line.bold;text:blue
CPU <-- F7 #blue;line:blue;line.bold;text:blue
CPU -- F8 #blue;line:blue;line.bold;text:blue
USU2 -left- F9 #blue;line:blue;line.bold;text:blue
CPU <.. F10 #red;line:red;text:red
USU3 -- F11 #red;line:red;text:red

  F1 --> F2
  F2 --> F3
  F3 --> F4
  F4 --> F5
  F5 --> F6
  F6 --> F7
  F7 --> F8
  F8 --> F9
  F9 --> F10
  F10 --> F11
}
@enduml