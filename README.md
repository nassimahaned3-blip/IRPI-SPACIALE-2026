markdown# 🛰️ Progiciel Expert : GeoIRPI v6.0
## Direction de l'Environnement — Wilaya de Tizi Ouzou
### Évaluation Thermodynamique Préliminaire par Screening de l'Indice IRPI et Masse Équivalente TNT

Ce dépôt présente le cadre algorithmique d'évaluation rapide et de screening pré-diagnostic des nouvelles demandes d'implantation industrielle à l'échelle de la commune de Larbaâ Nath Irathen [Local]. Le modèle exclut l'usage de périmètres d'exclusion ou de distances d'isolement arbitraires par défaut pour se concentrer exclusivement sur la quantification physique de la source de danger.

---

### 🔬 1. Formalisation Mathématique de l'Indice de Danger Source Normalisé
L'évaluation préliminaire quantifie l'Indice de Gravité Potentielle ($\Phi_{\text{Danger}}$) de la source. Le produit de la masse et de l'enthalpie est normalisé par une constante d'énergie de référence ($E_0 = 1 \text{ MJ}$) afin de garantir l'adimensionnalité rigoureuse de l'argument de la fonction logarithmique [Calcul] :

$$\Phi_{\text{Danger}} = \log_{10} \left( \frac{M_{\text{kg}} \times \Delta H_{\text{Substance (MJ/kg)}}}{1 \text{ MJ}} \right)$$

---

### 📐 2. Évaluation Spatiale des Effets de Surpression (Hopkinson-Cranz)
Le calcul des ondes de surpression mécanique accidentelles (seuil de 20 mbar pour les effets irréversibles) obéit à la loi de cubication tridimensionnelle en volume. Le modèle convertit la masse brute de produit stocké en masse équivalente de TNT ($M_{\text{TNT}}$) en intégrant l'enthalpie spécifique de la substance, le rendement thermique de l'explosion ($\alpha = 0,1$) et l'enthalpie de détonation de référence du TNT ($\Delta H_{\text{TNT}} = 4,69 \text{ MJ/kg}$) [Calcul] :

$$M_{\text{TNT}} = M_{\text{kg}} \times \left( \frac{\Delta H_{\text{Substance}}}{4,69} \right) \times \alpha$$

Le rayon d'impact physique réel au sol est déterminé à l'échelle 1:1 en mètres terrestres, excluant tout facteur de réduction linéaire à l'affichage écran afin de préserver la sincérité de l'analyse cartographique [Calcul] :

$$R_{\text{Thermodynamique}} = K \times M_{\text{TNT}}^{1/3}$$

*Où $K = 5$ représente le coefficient empirique international pour le seuil des effets létaux significatifs (300 mbar).*

---

### ⚖️ 3. Intégration du Verrou de Souveraineté National (Ouvrages Publics)
L'outil croise les coordonnées de l'établissement avec le tracé vectoriel des réseaux Sonelgaz via des calculs de distances géodésiques réels (ST_Distance). Il applique le seul disjoncteur réglementaire fixe et absolu dicté par le droit algérien : le couloir d'inconstructibilité de l'ouvrage public (Décret présidentiel n° 07-144) [Local, Finance, Calcul] :

$$\text{Verdict}_{\text{Souverain}} = \left[ D_{\text{Gazoduc}} \ge 150\,\text{m} \right]$$

La valeur numérique continue de l'indice $\Phi_{\text{Danger}}$ et le rayon $R_{\text{Thermodynamique}}$ font office d'indicateurs d'aide à la décision pour orienter les inspecteurs de la Direction de l'Environnement, sans couperet binaire ou pénalisation administrative forfaitaire artificielle [Finance, Calcul].
Utilisez le code avec précaution.💻 II. LE SCRIPT PYTHON RECENTRÉ ET SÉCURISÉ (GeoIRPI v6.0)Voici le code informatique complet et épuré. Il élimine définitivement les fonctions par morceaux et les seuils de 100/500/1500m pour se concentrer sur le calcul thermodynamique pur de l'IRPI et le couloir légal des 150m de la Sonelgaz [Calcul] :python
