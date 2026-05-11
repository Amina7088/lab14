# Бие даалт 14 — API Testing with Postman + Newman

## Ашигласан API
**DummyJSON** — https://dummyjson.com  
Auth шаардагдах endpoint-үүд болон CRUD үйлдлүүдийг тестэлсэн.

## Бүтэц

```
bie-daalt-14/
├── .github/
│   └── workflows/
│       └── api-tests.yml    # GitHub Actions CI
├── partA/
│   ├── SETUP.md             # API тайлбар
│   └── screenshot.png       # Эхний амжилттай request
├── postman/
│   ├── collection.json      # 8 request (Auth, Users, Posts)
│   ├── env.dev.json         # Dev environment
│   └── env.ci.json          # CI environment
├── reports/
│   └── api.html             # Newman HTML тайлан
├── README.md
└── REFLECTION.md
```

## Ажиллуулах заавар

### 1. Суулгалт
```bash
npm install -g newman newman-reporter-htmlextra
```

### 2. Local-д ажиллуулах
```bash
newman run postman/collection.json \
  -e postman/env.dev.json \
  --reporters cli,htmlextra \
  --reporter-htmlextra-export reports/api.html
```

### 3. HTML тайлан харах
`reports/api.html` файлыг browser-д нээнэ.

## Тестийн хамрах хүрээ

| Folder | Request | Төрөл |
|--------|---------|-------|
| Auth | Login | POST |
| Auth | Get My Profile | GET (token шаардана) |
| Auth | Delete post | DELETE |
| Users | Get all Users | GET (list) |
| Users | Get User by ID | GET (by id) |
| Users | User not found | GET (negative/404) |
| Posts | Create post | POST |
| Posts | Update Post | PUT |

**Нийт:** 29 assertion, 8 request, 1 pre-request script, 1 chain (Login → token → Get My Profile)
