# Документация Surpriz

Flask-сайт студии детских праздников и Next.js-админка. Домен: `animator-surpriz.uz`.

## Продукт

- [Product](Product.md) — путь клиента и бизнес-правила
- [Catalog](Catalog.md) — каталог персонажей и шоу-программ
- [Search](Search.md) — умный поиск в каталоге костюмов
- [Order-Builder](Order-Builder.md) — пошаговая сборка заказа: программа → персонажи → дата/время → контакты
- [Free-Choice-Bonus](Free-Choice-Bonus.md) — бесплатный бонус на выбор внутри программы
- [Customer-Portal](Customer-Portal.md) — личный кабинет клиента
- [Admin-Panel](Admin-Panel.md) — админка
- [Mobile-Bottom-Bar](Mobile-Bottom-Bar.md) — закреплённая нижняя навигация на мобильных

## Техника

- [Architecture](Architecture.md) — стек, модули, структура
- [Telegram-Integration](Telegram-Integration.md) — бот для уведомлений админам и Telegram Gateway для кодов входа
- [Migration-NextJS](Migration-NextJS.md) — приложение `webapp/` на Next.js и Flask-адаптер
- [V3-Cinematic](V3-Cinematic.md) — микросайт `/v3/`
- [site-design-guide](site-design-guide.md) — дизайн-система публичных страниц
- [Deployment](Deployment.md) — VPS, nginx, gunicorn, systemd, Let's Encrypt, порядок релиза

## Стек

- Python 3 / Flask 3 / gunicorn
- SQLite (WAL, FK on)
- Next.js 16 / React 19 (`webapp/`)
- nginx + Let's Encrypt (certbot)
- Ubuntu, systemd, ufw, fail2ban
- Telegram Bot API (уведомления) + Telegram Gateway (коды входа)

## Локально

```bash
.venv/bin/python app.py    # http://127.0.0.1:5000
```

## На сервере

```bash
ssh surpriz@<VPS_IP>
sudo systemctl restart surpriz-v2.service
```

Полный порядок релиза и отката — в [Deployment](Deployment.md).
