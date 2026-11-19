---
created: 2024-09-13
updated: 2024-09-17
completed: true
---
>[!algorithm] Algorithm: Huffman Coding
>Huffman coding is a procedure for generating optimal prefix codes. It assigns the longest codewords to least probable symbols:
>1. Take the two least probable symbols in the alphabet.
>2. Prepend bits $0$ and $1$ to current codewords of symbols.
>3. Combine these two symbols into a new symbol with probability equal to the sum of their probabilities.
>4. Repeat until all symbols are combined.
>
>Example Python code can be found [here](https://gist.github.com/mreid/fdf6353ec39d050e972b).
><u><b>e.g.</b></u>  Suppose $\mathcal{A}=\{a,b,c,d,e\}$ and $\mathbf{p}=(0.25, 0.25, 0.2, 0.15, 0.15)$. Then the whole procedure is as follows:
>![|500](https://dl.dropbox.com/scl/fi/cqu3u5bn0bc9g5chxh9tj/huffman_coding_eg.svg?rlkey=6xc63kio1m1wgwzzn6oiqqucn&st=zpkookss&dl=0)
>Therefore we have the output Huffman code $C=(00, 10, 11, 010, 011)$.

> [!proposition]
> The Huffman coding algorithm generates an optimal prefix code.
> 

>[!remark]
> Though Huffman coding is simple and efficient, as it assumes a fixed distribution of symbols, Huffman codes are the best possible symbol code, but symbol coding is not always the best type of code.
