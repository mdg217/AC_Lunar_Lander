# Lunar Lander
Il sistema proposto che dovrà essere controllato è il Lunar Lander, descritto da un modello a tre equazioni differenziali che ne esplicitano la dinamica in due dimensioni.
Il controllo della navicella è effettuato tramite due ingressi (due forze) $u_1$ e $u_2$ che permettono il movimento lungo i 3 gradi di libertà descritti dalle equazioni
$$
    \begin{cases}
        m\ddot{x} = u_1cos\theta - u_2sin\theta -c\dot{x}\\
        m\ddot{y} = u_1sin\theta + u_2cos\theta -mg -c\dot{y}\\
        J\ddot{\theta} = 4u_1
    \end{cases}
    \xrightarrow{}
    \begin{cases}
        \ddot{y} = \frac{1}{m}(u_1sin\theta + u_2cos\theta -mg -c\dot{y})\\
        \ddot{\theta} = 4\frac{u_1}{J}
    \end{cases}
$$
Per semplificare il sistema, senza perdere di generalità, consideriamo solo la dinamica relativa all'asse $y$ e alla rotazione della navicella dovuta al movimento lungo $\theta$ isolando le due variabili di accelerazione.
## Requisiti
*Il task di controllo che si vuole sviluppare è il **controllo** di un
lunar lander e del suo posizionamento a mezz’aria.* In particolare
quello che si vuole garantire è:

-   **Tracking di posizione sull’asse y** (la y desiderata sarà una
    traiettoria da seguire data da un **Trajectory Planner**);

-   **Stabilizzare l’angolo *θ* a 0** (o a qualunque riferimento a
    gradino desiderato);

-   **Eliminare la sovraelongazione** sulla posizione *y* e sull’angolo
    *θ* per garantire un buon tracking (in modo da evitare scontri con
    il suolo ad esempio);

-   **Reiettare il disturbo a gradino**;

-   **Garantire un tempo di assestamento *t*<sub>*a*</sub> ≤ 35*s*** per
    la posizione *y* e un tempo di assestamento minore per l’angolo *θ*.


## File

I file presenti nella cartella *\src* sono da utilizzare in coppia.\
#### **(Matlab & Simulink)**
- LQR: *LunarLanderLQRAndObserver*
- Pole Placement: *LunarLanderPolePlacementAndObserver*
- LQR + Azione Integrale: *LunarLanderLQRAndObserverIntegralAction*
- Pole Placement + Azione Integrale: *LunarLanderPolePlacementAndObserverIntegralAction*
- Osservatore *vs* Filtro di Kalman: *LunarLanderLQRKalman*

