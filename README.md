# 🛰️ Progiciel Expert : GeoIRPI v6.0
## Direction de l'Environnement — Wilaya de Tizi Ouzou
### Évaluation Composite de l'Index de Risque Probabiliste Intégré (IRPI) et Screening Spatial Multiniveau

Ce dépôt présente le cadre algorithmique d'évaluation rapide et de screening pré-diagnostic des nouvelles demandes d'implantation industrielle à l'échelle de la commune de Larbaâ Nath Irathen [Local]. Le modèle s'appuie exclusivement sur la formulation d'origine de l'index composite IRPI.

---

### 🔬 1. L'Équation Fondamentale de l'Indice IRPI Spatial
L'Index de Risque Probabiliste Intégré ($\text{IRPI}_{\text{Spatial}}$) mesure la criticité globale d'un établissement en combinant trois facteurs indissociables par un produit non compensatoire [Calcul] :

$$\text{IRPI}_{\text{Spatial}} = \Phi_{\text{Danger}} \times \pi_{\text{Défaillance}} \times \Omega_{\text{Environnement}}$$

#### A. Le Potentiel Énergétique Source Normalisé ($\Phi_{\text{Danger}}$)
L'argument de la fonction logarithmique est normalisé par une constante d'énergie de référence ($E_0 = 1$ MJ) pour assurer l'adimensionnalité rigoureuse de la charge brute disponible [Calcul] :

$$\Phi_{\text{Danger}} = \log_{10} \left( \frac{M_{\text{kg}} \times \Delta H_{\text{Substance (MJ/kg)}}}{1 \text{ MJ}} \right)$$

#### B. Le Facteur de Défaillance Cinétique ($\pi_{\text{Défaillance}}$)
Probabilité intrinsèque de rupture, d'incendie ou de fuite de confinement liée à la classe et à la nature technique de l'activité.

#### C. Le Facteur de Vulnérabilité Spatiale et Environnementale ($\Omega_{\text{Environnement}}$)
Coefficient fluide qui évalue l'éloignement géodésique réel de l'usine par rapport aux habitations traditionnelles de la Taddart et aux réseaux d'énergie [Local, Calcul].

---

### ⚖️ 2. Verrou de Souveraineté National Unique
Le logiciel maintient une correspondance d'échelle stricte à 1:1 en mètres au sol sur le fond de carte. L'arbre de décision n'applique qu'un seul et unique disjoncteur réglementaire bloquant dicté par le droit algérien : le couloir d'inconstructibilité de 150 mètres autour des gazoducs Sonelgaz (Décret présidentiel n° 07-144) [Local, Finance] :

$$\text{Verdict}_{\text{Souverain}} = \left[ D_{\text{Gazoduc}} \ge 150\,\text{m} \right]$$

Le score numérique de l'indice $\text{IRPI}_{\text{Spatial}}$ sert d'indicateur d'aide à la décision pour orienter et prioriser le contrôle des inspecteurs sur le terrain [Finance, Calcul].
