### Electronic Code Book (ECB)
This is the simplest mode of operation. Each block of plaintext is encrypted separately. The same plaintext block will always produce the same ciphertext block, which can be a security risk because patterns in the plaintext may be visible in the ciphertext.

Each block is encrypted and decrytped independantly. 
$$
c_i = E_k(m_i) \quad m_i = D_k(c_i)
$$
Meaning plaintext blocks give identical ciphertext blocks. Example of this would be the famous ECB tux penguin. 


```tikz
\usepackage{tikz}
\usetikzlibrary{calc}
\begin{document}
	\begin{tikzpicture}
    
        \foreach \x in {0, 1, 2} {
            \node (f\x) at ($\x*(2.5cm,0)$) [minimum size=1.25cm,rounded corners=1ex,fill=red!60,draw] {{\sc Enc}};
            \node (m\x) [above of=f\x, node distance=1.5cm] {$P_\x$};
            \node (k\x) [left of=f\x, node distance=1.5cm] {$k$};
            \node (c\x) [below of=f\x, node distance=1.5cm] {$C_\x$};
            \draw[-latex] (m\x) -- (f\x);
            \draw[-latex] (k\x) -- (f\x);
            \draw[-latex] (f\x) -- (c\x);
        }

        \begin{scope}
            \node at (6.4,0) {$\cdots\cdots$};
        \end{scope}

        \begin{scope}
            \node (f) at (8.8cm,0) [minimum size=1.25cm,rounded corners=1ex,fill=red!60,draw] {{\sc Enc}};
            \node (m) [above of=f, node distance=1.5cm] {$P_n$};
            \node (k) [left of=f, node distance=1.5cm] {$k$};
            \node (c) [below of=f, node distance=1.5cm] {$C_n$};
            \draw[-latex] (m) -- (f);
            \draw[-latex] (k) -- (f);
            \draw[-latex] (f) -- (c);
        \end{scope}
        
    \end{tikzpicture}
\end{document}
```

```tikz
\usepackage{tikz}
\usetikzlibrary{calc}
\begin{document}

    \begin{tikzpicture}
        
        \foreach \x in {0, 1, 2} {
            \node (f\x) at ($\x*(2.5cm,0)$) [minimum size=1.25cm,rounded corners=1ex,fill=blue!20,draw] {{\sc Dec}};
            \node (m\x) [above of=f\x, node distance=1.5cm] {$C_\x$};
            \node (k\x) [left of=f\x, node distance=1.5cm] {$k$};
            \node (c\x) [below of=f\x, node distance=1.5cm] {$P_\x$};
            \draw[-latex] (m\x) -- (f\x);
            \draw[-latex] (k\x) -- (f\x);
            \draw[-latex] (f\x) -- (c\x);
        }

        \begin{scope}
            \node at (6.4,0) {$\cdots\cdots$};
        \end{scope}

        \begin{scope}
            \node (f) at (8.8cm,0) [minimum size=1.25cm,rounded corners=1ex,fill=blue!20,draw] {{\sc Dec}};
            \node (m) [above of=f, node distance=1.5cm] {$C_n$};
            \node (k) [left of=f, node distance=1.5cm] {$k$};
            \node (c) [below of=f, node distance=1.5cm] {$P_n$};
            \draw[-latex] (m) -- (f);
            \draw[-latex] (k) -- (f);
            \draw[-latex] (f) -- (c);
        \end{scope}

    \end{tikzpicture}
    
\end{document}
```
### Ciphertext Feedback (CFB)
This mode turns a block cipher into a self-synchronizing stream cipher. It operates by encrypting the previous ciphertext block, then XORing the output with the current plaintext block to get the current ciphertext block.

XOR the plaintext block with the previous ciphertext block **after** encryption. 
$$
\begin{align*}
c_0 &= \text{initialisation vector} \newline 
c_i &= m_i \oplus E_k(c_{i-1})
\end{align*}
$$
```tikz
\usepackage{tikz}
\usetikzlibrary{calc}

\begin{document}

    \begin{tikzpicture}

        \foreach \x in {0, 1, 2} {
            \node (f\x) at ($\x*(2.5cm,0)$) [minimum size=1.25cm,rounded corners=1ex,fill=red!60,draw] {{\sc Enc}};
            \node (c\x) [below of=f\x, node distance=2.5cm] {$C_\x$};
            \node (k\x) [left of=f\x, node distance=1.5cm] {$k$};
            \node (p\x) [below of=f\x, node distance=1.5cm, circle, draw] {};
            \node (m\x) [left of=p\x, node distance=1.0cm] {$P_\x$};
            \draw[-] (p\x.north) -- (p\x.south);
            \draw[-] (p\x.east) -- (p\x.west);
            \draw[-latex] (m\x) -- (p\x);
            \draw[-latex] (f\x) -- (p\x);
            \draw[-latex] (k\x) -- (f\x);
            \draw[-latex] (p\x) -- (c\x);
        }

        \node (iv) [above of=f0, node distance=1.5cm] {$IV$};
        \draw[-latex] (iv) -- (f0);

        \foreach \x in {0, 1} {
            \draw[-latex] ($(c\x) + (0,0.6cm)$) -| +(0.8cm,3.4cm) -| ($(f\x.north) + (2.5cm,0)$);
        }

        \begin{scope}
            \node at (6.4,0) {$\cdots\cdots$};
        \end{scope}

        \begin{scope}
            \node (f) at (9.5cm,0) [minimum size=1.25cm,rounded corners=1ex,fill=red!60,draw] {{\sc Enc}};
            \node (c) [below of=f, node distance=2.5cm] {$C_n$};
            \node (k) [left of=f, node distance=1.5cm] {$k$};
            \node (p) [below of=f, node distance=1.5cm, circle, draw] {};
            \node (m) [left of=p, node distance=1.0cm] {$P_n$};
            \draw[-] (p.north) -- (p.south);
            \draw[-] (p.east) -- (p.west);
            \draw[-latex] (m) -- (p);
            \draw[-latex] (f) -- (p);
            \draw[-latex] (k) -- (f);
            \draw[-latex] (p) -- (c);
            \draw[-] ($(c) + (-2.5,0.6cm)$) -- ($(c) + (-1.7,0.6cm)$);
            \draw[-latex] ($(c) + (-1.7,0.6cm)$) -| +(0cm,3.4cm) -| (f);
        \end{scope}

    \end{tikzpicture}

\end{document}
```

- Sequential encryption and parallel decryption. 
- Self-synchronising and unidirectional. 

### Cipher Block chaining (CBC)
In this mode, each block of plaintext is XORed (a bitwise operation) with the previous ciphertext block before being encrypted. This means that each ciphertext block depends on all plaintext blocks processed up to that point.
$$
\begin{align*}
c_0 &= \text{intialisation vector} \\
c_i &= E_k(c_{i-1} \oplus m_i)
\end{align*}
$$

```tikz
\usepackage{tikz}
\usetikzlibrary{calc}

\begin{document}

    \begin{tikzpicture}
    
        \foreach \x in {0, 1, 2} {
            \node (f\x) at ($\x*(2.5cm,0)$) [minimum size=1.25cm,rounded corners=1ex,fill=red!60,draw] {{\sc Enc}};
            \node (p\x) [above of=f\x, node distance=1.5cm, circle, draw] {};
            \node (m\x) [above of=p\x, node distance=1cm] {$P_\x$};
            \node (k\x) [left of=f\x, node distance=1.5cm] {$k$};
            \node (c\x) [below of=f\x, node distance=1.5cm] {$C_\x$};
            \draw[-] (p\x.north) -- (p\x.south);
            \draw[-] (p\x.east) -- (p\x.west);
            \draw[-latex] (m\x) -- (p\x);
            \draw[-latex] (p\x) -- (f\x);
            \draw[-latex] (k\x) -- (f\x);
            \draw[-latex] (f\x) -- (c\x);
        }
        \node (iv) [left of=p0, node distance=1.5cm] {$IV$};
        \draw[-latex] (iv) -- (p0);

        \foreach \x in {0, 1} {
        \draw[-latex] ($(c\x) + (0,0.6cm)$) -| +(0.8cm,2.4cm) -- ($(p\x) + (2.4cm,0)$);

        \begin{scope}
            \node at (6.4,0) {$\cdots\cdots$};
        \end{scope}

        \begin{scope}
            \node (f) at (9.6cm,0) [minimum size=1.25cm,rounded corners=1ex,fill=red!60,draw] {{\sc Enc}};
            \node (p) [above of=f, node distance=1.5cm, circle, draw] {};
            \node (m) [above of=p, node distance=1cm] {$P_n$};
            \node (k) [left of=f, node distance=1.5cm] {$k$};
            \node (c) [below of=f, node distance=1.5cm] {$C_n$};
            \draw[-] (p.north) -- (p.south);
            \draw[-] (p.east) -- (p.west);
            \draw[-latex] (m) -- (p);
            \draw[-latex] (p) -- (f);
            \draw[-latex] (k) -- (f);
            \draw[-latex] (f) -- (c);
            \draw[-] ($(c) + (-2.5,0.6cm)$) -- ($(c) + (-1.7,0.6cm)$);
            \draw[-latex] ($(c) + (-1.7,0.6cm)$) |- + (0cm,2.4cm) -- (p);
        \end{scope}
        }

    \end{tikzpicture}

\end{document}
```

- Sequential encryption and parallel decryption 
- Self-Synchronising

### Output Feedback (OFB)
This mode also turns a block cipher into a stream cipher, but it operates by encrypting the previous output block (not the previous ciphertext block), then XORing the output with the current plaintext block to get the current ciphertext block.

$$
\begin{align*}
s_0 &= \text{initialisation vector} \\
s_i &= E_k(s_{i-1}) \\
c_i &= s_i \oplus m_i
\end{align*}
$$
- Sequential.
- Synchronous. 
- Allows batch processing. 
- Malleable. 
```tikz
\usepackage{tikz}
\usetikzlibrary{calc}

\begin{document}

    \begin{tikzpicture}

        \foreach \x in {0, 1, 2} {
            \node (f\x) at ($\x*(2.5cm,0)$) [minimum size=1.25cm,rounded corners=1ex,fill=red!60,draw] {{\sc Enc}};
            \node (c\x) [below of=f\x, node distance=2.5cm] {$C_\x$};
            \node (k\x) [left of=f\x, node distance=1.5cm] {$k$};
            \node (p\x) [below of=f\x, node distance=1.5cm, circle, draw] {};
            \node (m\x) [left of=p\x, node distance=1.0cm] {$P_\x$};
            \draw[-] (p\x.north) -- (p\x.south);
            \draw[-] (p\x.east) -- (p\x.west);
            \draw[-latex] (m\x) -- (p\x);
            \draw[-latex] (f\x) -- (p\x);
            \draw[-latex] (k\x) -- (f\x);
            \draw[-latex] (p\x) -- (c\x);
        }

        \node (iv) [above of=f0, node distance=1.5cm] {$IV$};
        \draw[-latex] (iv) -- (f0);

        \foreach \x in {0, 1} {
        \draw[-latex] ($(p\x) + (0,0.6cm)$) -| +(0.8cm,2.4cm) -| ($(f\x.north) + (2.5cm,0)$);
        }

        \begin{scope}
            \node at (6.4,0) {$\cdots\cdots$};
        \end{scope}

        \begin{scope}
            \node (f) at (9.6cm,0) [minimum size=1.25cm,rounded corners=1ex,fill=red!60,draw] {{\sc Enc}};
            \node (c) [below of=f, node distance=2.5cm] {$C_n$};
            \node (k) [left of=f, node distance=1.5cm] {$k$};
            \node (p) [below of=f, node distance=1.5cm, circle, draw] {};
            \node (m) [left of=p, node distance=1.0cm] {$P_n$};
            \draw[-] (p.north) -- (p.south);
            \draw[-] (p.east) -- (p.west);
            \draw[-latex] (m) -- (p);
            \draw[-latex] (f) -- (p);
            \draw[-latex] (k) -- (f);
            \draw[-latex] (p) -- (c);
            \draw[-] ($(p) + (-2.5,0.6cm)$) -- ($(p) + (-2.5,0.6cm)$);
            \draw[-latex] ($(p) + (-2.5,0.6cm)$) -| +(0.8cm,2.4cm) -| (f);
        \end{scope}

    \end{tikzpicture}

\end{document}
```

### Counter (CTR)
This mode turns a block cipher into a stream cipher. It operates by encrypting a counter value (which is incremented for each block), then XORing the output with the current plaintext block to get the current ciphertext block.

$$
\begin{align*}
s_0 &= \text{initialisation vector} \\
s_i &= E_k(s_0 || i) \\
c_i &= s_i \oplus m_i
\end{align*}
$$
- Parallel. 
- Synchronous. 
- Allows batch processing. 
- Malleable. 

```tikz
\usepackage{tikz}
\usetikzlibrary{calc}

\begin{document}

    \begin{tikzpicture}

        \foreach \x in {0, 1, 2} {
            \node (f\x) at ($\x*(2.5cm,0)$) [minimum size=1.25cm,rounded corners=1ex,fill=red!60,draw] {{\sc Enc}};
            \node (n\x) [above of=f\x, node distance=1.5cm] {Nonce, Ctr};
            \node (c\x) [below of=f\x, node distance=2.5cm] {$C_\x$};
            \node (k\x) [left of=f\x, node distance=1.5cm] {$k$};
            \node (p\x) [below of=f\x, node distance=1.5cm, circle, draw] {};
            \node (m\x) [left of=p\x, node distance=1.0cm] {$P_\x$};
            \draw[-] (p\x.north) -- (p\x.south);
            \draw[-] (p\x.east) -- (p\x.west);
            \draw[-latex] (m\x) -- (p\x);
            \draw[-latex] (n\x) -- (f\x);
            \draw[-latex] (f\x) -- (p\x);
            \draw[-latex] (k\x) -- (f\x);
            \draw[-latex] (p\x) -- (c\x);
        }

        \begin{scope}
            \node at (6.5,0) {$\cdots\cdots$};
        \end{scope}

        \begin{scope}
            \node (f) at (8.8cm,0) [minimum size=1.25cm,rounded corners=1ex,fill=red!60,draw] {{\sc Enc}};
            \node (n) [above of=f, node distance=1.5cm] {Nonce, Ctr};
            \node (c) [below of=f, node distance=2.5cm] {$C_n$};
            \node (k) [left of=f, node distance=1.5cm] {$k$};
            \node (p) [below of=f, node distance=1.5cm, circle, draw] {};
            \node (m) [left of=p, node distance=1.0cm] {$P_n$};
            \draw[-] (p.north) -- (p.south);
            \draw[-] (p.east) -- (p.west);
            \draw[-latex] (m) -- (p);
            \draw[-latex] (n) -- (f);
            \draw[-latex] (f) -- (p);
            \draw[-latex] (k) -- (f);
            \draw[-latex] (p) -- (c);
        \end{scope}

    \end{tikzpicture}

\end{document}
```



