- 👋 Hi, I’m @flannnnnncondulce
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
flannnnnncondulce/flannnnnncondulce is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
---> 
import tweepy
import random
import time
import schedule
import os

client_v2 = tweepy.Client(
    consumer_key=os.getenv("WBYk147cUuZSEAggICZ9OHkXY"),
    consumer_secret=os.getenv("XUZ9YHCIosj93QoCZmJvJ1nzoGxGdXVgB3rOJ8se1UWTYxaI6m"),
    access_token=os.getenv("1903802409647816704-U3CeBwrkKh1e2yUPYygfKONAszIfPx"),
    access_token_secret=os.getenv("cgTTK9gqd1xaHKcu0fJ7NYYrY3X8CARsh1ElfGMT5SbjH")
)

versos = [
     """Condenada a ser siempre ninguna\nCondenada a ser inoportuna\nCondenada a ser como la Luna""",
     """No sé si quiero resolver la duda\nNo sé si tengo una pregunta\nLo quiero evitar, tener que elegir\nDividirme en dos""",
     """A veces me reía a oscuras\nCuando fui libre sentí culpa\nTe quiero acostumbrar\nNo me hagas elegir alguna""",
     """Déjenme ponerle nombre a lo que soy\n¡Eso lo decido yo!\nLo voy a inventar\nAunque después más tarde lo destruya""",
     """No soy nada si me dividen en dos""",
     """No soy nada sin\nNo soy nada sin vos""",
     """Dicen que se esconde siempre en el mismo lugar\nSu verdad es su peor enfermedad\nDicen que se esconde siempre en el mismo lugar\nSu verdad es su peor enfermedad""",
     """Y corre a la salida\nCorre siempre hacia arriba\nSentado en la cima, sobre su capacidad\nNunca más pagaría, nunca más dolería\nSi corona amarilla, solo fue casualidad\nY lo quiere saber""",
     """Dicen que se esconde siempre en el mismo lugar\nSu verdad es su peor enfermedad""",
     """Ya no más querrá reconocerlo\nY abandonar su lugar\nSaber sentarse derecho anticipar""",
     """Sin problemas la vida pasa simple, aburrida\nPor sentir la emoción aprendió a causar dolor""",
     """Y ya fijo en la cima, pudo ver desde arriba\nSu corona amarilla, solo fue casualidad\n¿Por qué será?""",
     """buscando el mar\nescondido en el armario\nse le hace tarde y no se va\nsolo se sienta a esperar""",
     """una vez más\nsi pudiera entender\nque entre las sombras que hay detrás\nalgo más""",
     """y aunque nunca querrá admitirlo\nsabe qué hacer conmigo\n e intenta evitar todo espejo\npara no ver\na Nicolás""",
     """buscando el mar\nen el medio del desierto\nsigue mirando para atrás""",
     """No sé ni cómo te llamás\nPero cuando te me acercás\nEl piso se me prende fuego\nNo creo que sea casualidad que apareciste\nEn el lugar\nEn el que siempre pierdo el tiempo""",
     """Si no conozco a nadie más\nVoy a tener que esperar\nA poder ser como lo siento""",
     """Siempre lo mismo esta ciudad\nCuando se acerca navidad\nEl tiempo pasa aun más lento""",
     """Escondiéndome del sol, voy a imaginar\nQue me viniste a buscar""",
     """Y aunque me cueste aceptar\nTarde o temprano va a pasar""",
     """Y todavía es temprano y si me pongo a pensar\nSi nos volvemos a cruzar\nQuiero tomarte de la mano""",
     """Tu calor me hace mal\nDe cerca, bien, de lejos, mal\nDe cerca, bien, de lejos, mal\nDe cerca, bien, de lejos, mal""",
     """It's okay, but, not okay tho\nIt's okay, but I don't know why\nI'm trying to know what you really really think of me""",
     """Basta, olvídalo, no importa tanto\nNo es la primera vez que sufro tanto\nPor alguien más""",
     """Yo no sé qué es lo que te asusta\nSolo quiero ser el chico que te gusta\nNo, no lo hago más, yo puedo más""",
     """Para lo que ya conozco\nSiempre guardo algo más\nY aunque yo puedo estar solo\nHoy me puse a imaginar\nCómo será""",
     """Todo lo que no se puede\nMe hace falta mucho más\nY aunque yo puedo estar solo\nNo dejo de imaginar\nCómo será""",
     """Tu casa me hace sombra\nLa terraza, la alfombra\nLa gente de mi casa\nSe esconde del que cobra""",
     """Cuando me metí adentro\nSe apagaron los vientos\nEl calor de mi casa\nEs más fuerte en invierno""",
     """Las heridas me las quedo\nSon regalos para mí\nLas cenizas son del viento\nY ya se empiezan a ir""",
     """Yo vengo de una oscuridad\nQue no me deja salir""",
     """Y aunque vea lo que busco y quiera\nNo puedo encontrarlo""",
     """¿Dónde vas a ir sin ver dónde estás ahora?""",
     """Por dejar\nQue llueva sobre mí\nSe me cerró la puerta y ahora estoy\nPensando sólo en mí""",
     """tu innecesaria decisión\nde no entender las cosas\ntu ideología desistió, y ahora yo\nme quedo así\npensando en qué me voy a convertir""",
     """me resisto a olvidar""",
     """No esperaba nada\nni alegría ni dolor\npero estaba eso dentro de mí""",
     """no entiendo casi nada\npero algo debe decir\nno fue lo que parece\nefecto 17""",
     """no fue lo que parece\ntuve que aceptar el ruido\ny hacerlo salir\nsalir de mí""",
     """Me relaja acobardarme, porque siento que es más fácil\nYo prefiero hacerte reír""",
     """Quiero convidarte la ternura, que al menos hasta ahora,\nSolo en sueños te cedí""",
     """¿Cómo es una vida sin temor?\nComo un terremoto sin temblor.\nEs anticiparse a lo peor\nY culpa de eso,\nSolo de eso,\nPerderse lo mejor.""",
     """Todos los colores a la vez, ya estoy imaginándolo\nTodos los colores a la vez""",
     """Todas las figuras a la vez, ya estoy imaginándolo""",
     """Y está bien si hago con mis ojos remolinos para refugiarme\nPara que el cielo pueda ver\nTodos los colores a la vez""",
     """Debo estar pensando que necesitas\nAlgo está pasando pero en otro lugar\nParalizando el tiempo buscando una señal""",
     """Algo está pasando pero en otro lugar\nA todo le voy poniendo la misma intensidad\nY ahora creo que la salida está en la incomodidad""",
     """Algo me está pegando, no te puedo mirar\nQuiero saber qué pasa y no lo quiero aceptar""",
     """Lento me acerqué y como un rayo se me escapó\nLos colores que me vestían me delataron""",
     """Tenía un brillo en la mirada que me encantaba\ny aunque temí que me atacara no me hizo nada""",
     """Cuando lo vi sentí una magia que me abrazaba\nPorque entendí que no sé nada de lo que pasa""",
     """Con la información que tenía no me alcanzaba\nQuién me iba a creer que existía, estaba ahí""",
     """Nadie lo pudo ver, solo yo, y eso no es poco\nCuando lo vi sentí una magia que me abrazaba\nPorque entendí que no sé nada de lo que pasa""",
     """El tiempo en que hay dolor\nNo puede ser, no debe ser esquivado\nAlgo hay que atravesar ahora""",
     """Tuve que pensar sin parar\nAnalizarlo todo, pero así no es\nTomé un atajo para huir de mí""",
     """Es que no se puede esquivar""",
     """La parte que nos mueve, eso es aprender""",
     """Intenté llegar a otro lugar\nCompletamente solo, subir de nivel""",
     """Una ciudad con todos escondidos\n Que casualidad, yo hoy he decidido\nQue todo lo que hay es hermoso\nY todo lo puedo probar""",
     """No volveré a pensar si todo sale mal\nPierdo y otra vez será\nPara mí es normal""",
     """Voy a intentar haciéndolo distinto\nMe quise acordar, pero siempre me olvido\nQue voy tropezando con todo""",
     """De tanto navegar en un mismo lugar\nTodo lo que puedo imaginar\nPara mí es real""",
     """Hay que salvar a la luna de toda codicia\nPorque ella sabe las formas que todos tendrán""",
     """Hay que salvar cada luz para que podamos ver el sol""",
     """Cuando el poeta divisa el amor\nEnvuelve el cielo de plumas y tinta y papel""",
     """Con su poesía logró vencer al único Dios del fin""",
     """Cuando el pirata que vuelve sin ala\nBaila las sombras y sombra de un mes pasado""",
     """Espera el amanecer buscando dónde esconderse\nHaber gozado de verse velando su propia sed""",
     """tengo el corazón de un animal""",
     """Volverás o no vas, me dijo y se borró""",
     """Debes saber que ando a por ti""",
     """Te querés mostrar, al mundo le da igual\nCreaste un enemigo para pasarlo mal""",
     """yendo despacio te podés chocar igual""",
     """Volverá a por más, y me voy a ocupar\nEl monstruo es legendario, es más difícil de atrapar""",
     """Las palabras más importantes las dejé para después""",
     """No me asusto con el frío, pero igual yo muevo el pie""",
     """Creés que es lo que pasa, si me olvido me casa\nSe prende a mi cabeza, me voy a liberar""",
     """Volverá a por más, me hará ver el error\nvoy a ocupar hasta que no lo vea más""",
     """Ahora mi alma sabe\nQue es lo importante\nEstar el mejor""",
     """Yo me di cuenta\nTus pies nunca tocan el suelo\nY la otra vuelta\nLograste sacarme de acá""",
     """No pude arreglarme\nAntes de venir\nNo puedo hacerlo solo\nNo entiendo que puedo arreglar""",
     """Soñé que estabas acá, así que vine\nMe sirve para empezar, si estamos los dos""",
     """Soñé que estabas acá, así que vine""",
     """Cantame al oído\nReíte conmigo\nVeo algo mejor del futuro\nQué me mostrás""",
     """Ay, te vas ahí y ni te pude hacer notar\nQue todo lo que hay llega hasta el fin\nNunca pude verlo hasta que entendí""",
     """Y antes de venir, preparé mi piel una vez más\nYendo despacio, te podés chocar igual""",
     """Ay, la novedad va a crecer tan lejos\nTe va a buscar cuando te olvides\nQue algo nuevo va a venir""",
     """sigo dando vueltas y no me detengo a mirar""",
     """me sirve para empezar si estamos los dos...""",
     """Otra vez pensando, no puedo gritar""",
     """ESTA PARTE QUE SE ENTIENDA, SOLO ME IMPORTA LA MERIENDA!""",
     """dejemos todo atrás\nun rato nada más\nme vuelvo a levantar""",
     """vos no decidís cómo llegar a tu destino\nte tocan esas cosas que encontrás en el camino""",
     """por eso por favor escuchá bien lo que te digo: a veces no te ves hasta mirar a tus amigos""",
     """hoy las otras flores te encontraron florecido\npor fin te diste cuenta de todo lo que has crecido""",
     """si hay algo diferente vos sabés lo que se siente\ntenías la respuesta pero no estabas consciente""",
     """a veces no te ves hasta mirar a tus amigos""",
     """vos sabes bien que es lo importante""",
     """SOLO ME IMPORTA LA MERIENDA""",
     """stream Lichi!""",
     """SOLO ME IMPORTA LA MERIENDA""",
     """stream Lichi!""",
     """SOLO ME IMPORTA LA MERIENDA""",
     """stream Lichi!"""
]

client_v2 = tweepy.Client(
    consumer_key=API_KEY,
    consumer_secret=API_SECRET,
    access_token=ACCESS_TOKEN,
    access_token_secret=ACCESS_TOKEN_SECRET
)

def post_tweet(text):
    try:
        if len(text) <= 280:
            client_v2.create_tweet(text=text)
            print(f"¡Mensaje publicado! Fue: {text}")
        else:
            print(f"El mensaje es demasiado largo ({len(text)} caracteres), máximo 280. Saltando este verso.")
    except tweepy.TweepyException as e:
        print(f"Error específico de Twitter: {e}")
    except Exception as e:
        print(f"Error inesperado: {e}")

def publicar_verso():
    print("Eligiendo un verso...")
    verso_aleatorio = random.choice(versos)
    print(f"Verso elegido: {verso_aleatorio}")
    post_tweet(verso_aleatorio)

schedule.every(2).hours.do(publicar_verso)

print("Iniciando el bot...")
publicar_verso()

while True:
    schedule.run_pending()
    time.sleep(60)
  
