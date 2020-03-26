
# Процедурно генерируемые связные квесты и выполнение квестов НПС
<details>
  <summary>Процедурно генерируемые связные квесты</summary>
***
Идея данной системы позаимствонна у Alife. Планировщик, основываясь на множестве условий и событий в игровом мире дает цели ГГ и НПС, они в свою очередь должны достигнуть определеного радиуса до цели, и если нужно выполнить условие выполнения квеста (убийство мобов, взятие предмета и тп). Далее планировщик может сгенерировать новые (под)цели для достижения основной цели.
Экземпляр планировщика генерирует свою линию квестов, в игре могут быть запущены несколько экземпляров планировщиков.
Планировщику в начале задаётся цель и НПС(ы), возможно ГГ, которые будут выполнять квесты, каждый НПС под планировщиком и активным заданием пытается выполнить цель, достигая цели непосредственно "пешком". Из-за того, что Alife непредсказуемый - с НПС(ами)  может случиться что угодно (смерть, кража квестового предмета и тд.). Получается что выполнение каждой квестовой линии планировщика будет уникально, при этом главная цель линии сохраняется.

### Примеры
**Цель:** Артефакт.

**Работодатели:** Сахаров, Волкодав, Бармен.

**Исполнители:** Вася, Петя, ГГ.

Пояснение:<br>
*Одиночка Вася получает квест от Сахорова на доставку нового единственного артефакта из далёкого и страшного места Зоны. Наёмник Петя получает такой же заказ от Волкодава. ГГ получет заказ от Бармена*
Развития событий:<br> 
- Вася дошёл до артефакта, взял его и отнес Сахорову, Петя не нагнал Васю, ГГ не выполнял квест.
- Вася дошёл до артефакта, застаёт на месте ГГ с артефактом, происходит разговор или пальба, по пути назад на ГГ нападает Петя.
- Петя дошёл до артефакта, взял его но по пути его убили мутанты, (ГГ как бы случайно получаерт сообщение о месте где искать труп),  - Петя наход труп первым и забирает артефакт и доставляет Сахорову (у ГГ задание провалено)

Это очень топорные и простые примеры, но на них видно, что ситуации могут складываться по разному в огромном количестве вариаций.
</details>

<details>
  <summary>Выполнение квестов НПС</summary>
***
Для того чтобы НПС могли выполнять квесты им нужно создать специальную схему поведения, схема эта написана таким образом, что планировщик квестов подставляет координаты целей, чтобы НПС шёл к этим координатам, по достижению координат - схема сигнализирует планировщику и ждет новых целей или отпускает НПС.
</details>

<details>
	<summary>Пример работы</summary>
Для тестирования и просто просмотра работы системы - скачайте сохранение из папки "save" данного репозитория, загрузите его, навидите прицел на любого НПС, выйдите в главное меню, нажмите "U", вернитесь в игру. В игре заспавнится НПС-работодатель и объект-цель "Ноутбук". Можно проследить как назначенный НПС будет двигаться к НПС-работодателю, затем к цели "Ноутбуку", и потом обратно к работодателю (для отчета). Цель-объект можно переносить в и наблюдать как НПС будет на это реагировать.
</details>
<a href="https://youtu.be/otGTh_2ASr0" target="_blank">Видео пример</a>

#### Ставиться на Call of Chernobyl 1.4.12
