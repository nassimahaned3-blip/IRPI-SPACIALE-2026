# 🛰️ Progiciel Expert : GeoIRPI v6.0
## Direction de l'Environnement — Wilaya de Tizi Ouzou
### Matrice d'Aide à la Décision Préliminaire (Screening) par Approche Linéaire et Multi-Verrous Réglementaires

Ce dépôt présente le cadre algorithmique d'évaluation rapide et de triage des nouvelles demandes d'implantation industrielle à l'échelle de la commune de Larbaâ Nath Irathen. Le modèle élimine les effets de masque et les compressions logarithmiques pour restituer la proportionnalité physique des risques.

---

### 🔬 1. Formalisation du Potentiel Source Linéaire
L'évaluation quantifie l'Indice de Gravité Potentielle ($\Phi_{\text{Danger}}$) à partir de la charge énergétique brute normalisée par une constante de référence ($E_0 = 10^6 \text{ MJ}$), assurant la linéarité de la menace face aux stockages de grande envergure :

$$\Phi_{\text{Danger}} = \frac{M_{\text{kg}} \times \Delta H_{\text{Substance (MJ/kg)}}}{10^6 \text{ MJ}}$$

---

### 📐 2. Indice Composite IRPI sans Effet de Masque
Afin d'éviter qu'une faible probabilité de défaillance cinétique ($\pi_{\text{Défaillance}}$) n'annule ou ne masque l'impact d'un sinistre majeur en zone habitée, l'architecture abandonne la structure strictement multiplicative au profit d'une formulation combinée pondérée :

$$\text{IRPI}_{\text{Spatial}} = \Phi_{\text{Danger}} \times \left( \beta_1 \cdot \pi_{\text{Défaillance}} + \beta_2 \cdot \Omega_{\text{Environnement}} \right)$$

---

### ⚖️ 3. Arbre de Décision par Matrice de Multi-Verrous Absolus
L'arbitrage de conformité s'affranchit du disjoncteur unique. Le verdict final applique de manière simultanée trois fonctions indicatrices d'Iverson distinctes, issues du Journal Officiel de la République Algérienne :

$$\text{Verdict}_{\text{Final}} = [\text{Verrou}_{\text{Sonelgaz}}] \times [\text{Verrou}_{\text{Hydrique}}] \times [\text{Verrou}_{\text{Scolaire}}]$$

*   **Ouvrage Énergétique (Décret n° 07-144) :** $[\text{Verrou}_{\text{Sonelgaz}}] = [D_{\text{Gazoduc}} \ge 150\,\text{m}]$
*   **Protection des Ressources en Eau (Loi n° 05-12) :** $[\text{Verrou}_{\text{Hydrique}}] = [D_{\text{Oued}} \ge 50\,\text{m}]$
*   **Sanctuarisation des Périmètres Scolaires (Loi n° 04-20) :** $[\text{Verrou}_{\text{Scolaire}}] = [D_{\text{École}} \ge 100\,\text{m}]$

Toute violation d'une seule de ces distances légales fait tomber le produit d'Iverson à 0, entraînant le rejet immédiat et automatisé du dossier d'urbanisme (Décret n° 15-19).
