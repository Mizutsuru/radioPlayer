#!/bin/bash

declare -A radios=(
    [1]="https://www.gayfm.de/listen.asx|Gay FM [Electro, EDM, Pop, Remixes]"
    [2]="https://ice4.somafm.com/poptron-128-aac|PopTron [Pop, Indie]"
    [3]="https://ice6.somafm.com/u80s-128-aac|UnderGround 80s [SynthPop, New Wave]"
    [4]="https://ice2.somafm.com/seventies-128-aac|Left Coast 70s [Mellow Rock]"
)

mostrar_menu() {
    echo "Selección de emisora:"
    for i in $(echo "${!radios[@]}" | tr ' ' '\n' | sort -n); do
        descripcion=$(echo "${radios[$i]}" | cut -d'|' -f2)
        echo "$i) $descripcion"
    done
    echo "0) Salir"
}

reproducir_radio() {
    local seleccion=$1
    if [[ $seleccion -eq 0 ]]; then
        echo "Saliendo..."
        exit 0
    elif [[ -n "${radios[$seleccion]}" ]]; then
        url=$(echo "${radios[$seleccion]}" | cut -d'|' -f1)
        echo "Reproduciendo emisora... Presiona Enter para detener."
        
        cvlc --quiet "$url" &
        vlc_pid=$!
        
        read -p ""
        
        kill $vlc_pid 2>/dev/null
        
        echo "Reproducción detenida."
    else
        echo "Opción no valida."
    fi
}

while true; do
    mostrar_menu
    read -p "Selecciona el número de la emisora: " seleccion
    reproducir_radio $seleccion
    clear
done

