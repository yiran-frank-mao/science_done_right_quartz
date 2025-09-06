---
created: 2024-02-26
updated: 2024-09-17
---
## Fundamentals of Digital Images

>[!definition] 
>**Def**  <i><u>Image</u></i>
>An image is a [[Relations and Functions#^862dba|function]] $I\colon S \to \R^{n}$ of spatial coordinates, where $S\subset \R^{2}$ and $I(x,y)$ is the intensity of the image at that point (pixel).

## Colour Spaces

>[!definition] 
>**Def**  <i><u>RGB Space</u></i>
>The RGB space has three coordinates $(R,G,B)$ denotes the red, green and blue channels respectively. The ranges are $R,G,B\in[0,255]$.

>[!definition] 
>**Def**  <i><u>HSV Space</u></i>
>The HSV space has three coordinates $(H,S,V)$ denotes the hue, saturation and value(brightness) respectively. The ranges are $H\in[0,360^{\circ}]$, $S\in[0,1]$ and $V\in[0,1]$.
>![|300](https://i.imgur.com/hGiRVju.png)

>[!comment]
>Advantages of HSV colour-space:
>- **Intuitive representation of colors**: It provides an intuitive representation of colors that is more natural to the human perception of color.
>- **Separation of color and brightness**: It separates color and brightness information into different components, which makes it easier to adjust color without affecting brightness.
>- **Robustness to lighting variations**: It is more robust to lighting variations than other color spaces, such as RGB, because it separates brightness information from color information.
>- **Approximately uniform color spacing**: The HSV color space has a nearly uniform color spacing, which means that the perceptual difference between colors is roughly equal.
>$\quad$

>[!theorem] 
>**Thrm**  One can transform from RGB space to HSV space by following formula: Let $C=\max(R,G,B)-\min(R,G,B)$. Then $$\begin{aligned}V&=\max(R,G,B) \\H&=\begin{cases}0,\quad &\text{if } C=0 \\ 60^{\circ}\left(\frac{G-B}{C}\right), \quad &\text{if } V=R \\ 60^{\circ}\left(2+\frac{B-R}{C}\right), \quad &\text{if } V=G \\60^{\circ}\left(4+\frac{R-G}{C}\right), \quad &\text{if } V=B \end{cases} \\S &= \begin{cases}0, \quad &\text{if } V=0 \\\frac{C}{V}, \quad&\text{otherwise}\end{cases}\end{aligned}$$