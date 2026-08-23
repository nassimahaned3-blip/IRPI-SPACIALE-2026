# Formalisation Mathématique et Modèle Homothétique

Le calcul de l'Index de Risque Probabiliste Intégré ($IRPI_{\text{Spatial}}$) repose sur une fonction produit non compensatoire de type Cobb-Douglas, indexée sur l'effet multiplicateur de la masse de stockage confinée réelle ($M_{\text{kg}}$) :

$$\Phi_{\text{Danger}} = \log_{10} \Big( \text{Masse}_{\text{Stockée (kg)}} \times \text{Enthalpie}_{\text{Substance (MJ/kg)}} \Big)$$

Le rayon de danger d'effet létal thermodynamique induit par l'onde de choc s'évalue selon la loi physique des gaz :

$$R_{\text{Thermodynamique}} = 15 \times \sqrt[3]{\text{Masse}_{\text{Stockée (kg)}}}$$

Afin de neutraliser les pathologies de saturation visuelle des moniteurs sur l'interface graphique de l'APC, le moteur visuel applique une réduction homothétique d'échelle d'un facteur de dix, découplant le flux de calcul réel du rendu de l'écran :

$$R_{\text{Affichage Écran}} = \frac{R_{\text{Thermody
