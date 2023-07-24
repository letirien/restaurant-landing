<script>
import { onMount } from 'svelte';
import L from 'leaflet'
import { icon } from "leaflet"

const ICON = icon({
  iconUrl: "/marker.png",
  iconSize: [32, 32],
})
// Initialisation de la carte

onMount(() => {
    const map = L.map('map', { attributionControl: false }).setView([48.573405, 7.752111], 13);

    // Ajout d'une couche de tuiles (vous pouvez en utiliser d'autres, par exemple, Mapbox, etc.)
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png').addTo(map);
    L.attributionControl = false
    // Fonction pour afficher un marqueur à partir de l'adresse
    function afficherMarqueur(adresse) {
    // Utilisation d'une API de géocodage (ici, OpenStreetMap Nominatim)
    const url = `https://nominatim.openstreetmap.org/search?format=json&q=${encodeURIComponent(adresse)}`;

    fetch(url)
        .then(response => response.json())
        .then(data => {
        if (data.length > 0) {
            const lat = parseFloat(data[0].lat);
            const lon = parseFloat(data[0].lon);
            // Ajout du marqueur à la carte
            L.marker([lat, lon],{icon: ICON}).addTo(map);
            // Déplacer la carte pour centrer le marqueur
            map.setView([lat, lon], 13);
        } else {
            console.error('Adresse introuvable');
        }
        })
        .catch(error => {
        console.error('Erreur lors de la récupération des coordonnées géographiques', error);
        });
    }

    // Appel de la fonction pour afficher le marqueur
    const adresseALocaliser = "8 rue Perle, Schiltigheim, 67300";
    afficherMarqueur(adresseALocaliser);
});
</script>

<div id="map" style="width: 100%; height: 400px;"></div>
