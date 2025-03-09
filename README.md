# Modulo6-Integrador
Integrador de sistemas operativos

CODIGO DE INSTALACIÓN (tuve algunos inconvenientes y lo tuve que instalar distinto)

sudo dpkg -- configure -a
sudo apt-get install -f
sudo apt update
sudo apt install espeak )

CODIGO DE CREACIÓN DEL ARCHIVO:
mkdir recordatorio.sh
nano recordatorio.sh

CODIGO DENTRO DE NANO
#!/bin/bash

while true; do
clear

read -p "Ingrese el mensaje del recordatorio: " mensaje
read -p "Ingrese el tiempo de espera en segundos: " tiempo

echo "El recordatorio se ha guardado correctamente. El mensaje '$mensaje' se notificará en $tiempo segundos."

sleep $tiempo

espeak -v es "Recordatorio: $mensaje"

cat <<EOF
Seleccione una opcion:
1- Programar otro recordatorio.
2- Salir
EOF
read -p "Ingrese una opción (1 o 2):" reply
        case "$reply" in
            1) continue
            ;;
            2) exit 0
            ;;
            *) echo "Opción inválida. Ingrese otro número."
            ;;
        esac
done

