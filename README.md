Um den Button so richtig "jelly-like" (geleeartig) wirken zu lassen, müssen wir den Glanz verstärken und die Form beim Klicken etwas extremer verzerren.

Hier ist der Code für einen Jelly-Button in einem schicken Cyan-Blau:

HTML
HTML

<button class="jelly-btn">CLICK ME</button>
CSS (Der Jelly-Look)
CSS

.jelly-btn {
  /* Farben & Form */
  background: linear-gradient(135deg, #00d2ff 0%, #3a7bd5 100%);
  color: white;
  border: none;
  padding: 20px 45px;
  font-size: 1.2rem;
  font-weight: bold;
  border-radius: 50px;
  cursor: pointer;
  position: relative;
  outline: none;

  /* Weiche Schatten für den "schwebenden" Look */
  box-shadow: 
    0 15px 25px rgba(58, 123, 213, 0.4),
    inset 0 -8px 12px rgba(0, 0, 0, 0.1),
    inset 0 8px 12px rgba(255, 255, 255, 0.3);

  transition: all 0.2s ease;
}

/* Der Glanz-Effekt oben drauf */
.jelly-btn::before {
  content: "";
  position: absolute;
  top: 5px;
  left: 15%;
  width: 70%;
  height: 35%;
  background: linear-gradient(to bottom, rgba(255,255,255,0.4), transparent);
  border-radius: 20px;
}

/* Die Jelly-Animation beim Klicken */
.jelly-btn:active {
  transform: scale(0.9) translateY(5px);
  box-shadow: 
    0 5px 10px rgba(58, 123, 213, 0.4),
    inset 0 8px 15px rgba(0, 0, 0, 0.2);
  /* Ein kurzer "Wabbel"-Effekt */
  animation: jelly-wobble 0.3s ease-in-out;
}

@keyframes jelly-wobble {
  0% { transform: scale(0.9, 0.9); }
  50% { transform: scale(1.1, 0.8); }
  100% { transform: scale(0.9, 0.9); }
}

👉 Hier zur Live-Demo


Was macht diesen Stil  (jelly)?
Der innere Glanz (::before): Das weiße Element oben im Button lässt ihn wie Glas oder eine glänzende Oberfläche wirken, genau wie bei einem Gummibärchen oder Gelee.

Die jelly-wobble Animation: Wenn du den Button loslässt oder drückst, verzieht er sich kurz (wird breiter und flacher). Das imitiert die Trägheit einer weichen Masse.

Doppelte Inset-Schatten: Wir nutzen einen hellen Schatten oben und einen dunklen unten innerhalb des Buttons, um Volumen zu erzeugen.

Kleiner Tipp für den "Squish-Faktor"
Wenn du willst, dass er noch mehr nachgibt, kannst du im @keyframes die Werte für scale noch extremer einstellen (z.B. 1.2, 0.7).

Soll ich dir ein komplettes Beispiel mit einem passenden Hintergrund-Design erstellen, damit das Ganze wie ein modernes Dashboard aussieht?
