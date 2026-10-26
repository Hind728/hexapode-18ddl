# hexapode-18ddl
# Robot hexapode 18 DDL : cahier des charges

> Projet personnel, module de robotique, USTHB. Simulation ROS2/Gazebo + prototype physique d'une patte.

## 1. Contexte et problématique

Les robots à pattes franchissent des terrains où les roues échouent. L'hexapode est un bon compromis : ses 6 pattes lui donnent une stabilité statique permanente et une tolérance à la panne d'une patte. En contrepartie, sa commande (18 actionneurs coordonnés) est complexe.

## 2. Objectif général

Concevoir, modéliser et simuler un hexapode capable de marcher et de tourner, puis valider le modèle avec une patte physique réelle.

## 3. Objectifs spécifiques

- Modéliser la cinématique directe et inverse d'une patte 3 DDL (coxa, fémur, tibia)
- Générer les allures de marche : tripode, ondulatoire, puis ripple
- Construire le modèle URDF du robot complet et le simuler (ROS2 + Gazebo)
- Réaliser et piloter une patte réelle (servomoteurs + microcontrôleur)
- Comparer les résultats simulation / mesures sur la patte réelle

## 4. Architecture

- **Mécanique** : corps hexagonal, 6 pattes × 3 DDL = 18 DDL
- **Logiciel** : planification des trajectoires → cinématique inverse → contrôleurs articulaires (nœuds ROS2)
- **Physique** : ESP32 / Arduino + 3 servomoteurs + alimentation dédiée

## 5. Capteurs et actionneurs

| | Simulation | Prototype physique |
|---|---|---|
| Actionneurs | 18 servos | 3 servos (1 patte) |
| Capteurs | IMU, positions articulaires, contacts au sol | Retour de position des servos |

## 6. Exigences

| Type | Exigence |
|---|---|
| Fonctionnelle | Marche en ligne droite, rotation sur place, changement d'allure |
| Fonctionnelle | Stabilité : le centre de gravité reste dans le polygone de support |
| Technique | Erreur de positionnement du pied < 5 mm en simulation |
| Technique | Boucle de commande ≥ 50 Hz |
| Contrainte | Réalisation en 8 semaines, matériel à faible coût |

## 7. Outils et technologies

ROS2, Gazebo, URDF, Python / C++, MATLAB (validation de la cinématique), Arduino / ESP32.

## 8. Planning (8 semaines)

| Semaine | Tâche |
|---|---|
| 1 | Cahier des charges, cinématique d'une patte |
| 2 | Cinématique inverse + validation MATLAB |
| 3 | Modèle URDF + simulation d'une patte |
| 4 | Hexapode complet sous Gazebo |
| 5 | Allure tripode |
| 6 | Autres allures + rotation |
| 7 | Patte physique + comparaison simulation / réel |
| 8 | Rapport final + démonstration |

## 9. Résultats attendus

- Hexapode simulé capable de marcher en ligne droite et de tourner
- Patte réelle validant la cinématique
- Code source, modèle URDF et rapport disponibles dans ce dépôt

## 10. Livrables

- [x] Cahier des charges (ce document)
- [ ] Modèle cinématique + validation MATLAB
- [ ] Simulation Gazebo de l'hexapode
- [ ] Prototype d'une patte physique
- [ ] Rapport final et démonstration
