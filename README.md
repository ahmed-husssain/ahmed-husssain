<!--
  You read source before you hire. Respect.
  That's exactly how I approach every codebase I inherit.

  Backend that actually runs: https://ahmedhusssain.vercel.app/
  Problem worth solving?     ahmedhusssain.dev@gmail.com
-->

<div align="center">

```
┌──────────────────────────────────────────────────────────────┐
│                AHMED HUSSAIN  //  backend engineer           │
│         C# · ASP.NET Core · PostgreSQL · SQL Server          │
│            shipping production code @ shifa healthcare       │
└──────────────────────────────────────────────────────────────┘
```

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=16&duration=2600&pause=1200&color=58A6FF&center=true&vCenter=true&width=620&lines=Backend+Engineer+%7C+C%23+.NET+%26+SQL+Server;Idempotent+APIs.+Because+double-charging+hurts.;Clean+schemas+first.+Features+second.;Runner-Up+%40+Aptech+Vision+2025;Shipping+Production+Code+%40+Shifa+Healthcare)](https://ahmedhusssain.vercel.app/)

[![Portfolio](https://img.shields.io/badge/Website-0d0d0d?style=flat-square&logo=vercel&logoColor=white)](https://ahmedhusssain.vercel.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/ahmed-husssain)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:ahmedhusssain.dev@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/ahmed-husssain)
![Profile Views](https://komarev.com/ghpvc/?username=ahmed-husssain&style=flat-square&color=58A6FF&label=profile+views)

</div>

---

```sql
SELECT 
    [Engineer]    = 'Ahmed Hussain',
    [Location]    = 'Karachi, Pakistan (PKT / UTC+5)',
    [CurrentRole] = 'Software Developer @ Shifa Healthcare (Remote)',
    [CoreStack]   = 'C# · ASP.NET Core · SQL Server · PostgreSQL',
    [Focus]       = 'Concurrency Control · Clean Schemas · Idempotent APIs'
WHERE 
    UnhandledExceptions = 0 AND IdempotencyGuaranteed = 1;
```

---

## Live Systems

| Project | What it is & Architecture | Stack | Status |
|:--------|:--------------------------|:------|:------:|
| **[Online Art Gallery](https://gallrex.runasp.net)** | Live auction engine with EF Core optimistic concurrency (`RowVersion`) & auto-settlement worker | ASP.NET Core MVC · EF Core · SQL Server · SignalR | `RUNNING` |
| **[Shifa Management System](https://github.com/ahmed-husssain/ShifaMangementSystem)** | Clinical ERP with atomic row locks (`SELECT ... FOR UPDATE`) & automated WhatsApp invoice pipeline | Flutter · Supabase / PostgreSQL · Riverpod | `SHIPPED` |
| **[Mockrithm](https://mockrithm.me)** | AI technical interview simulation engine — **Runner-Up @ Aptech Vision 2025** | Next.js · Firebase · Algorithms | `LIVE` |
| **[E-Books Platform](https://github.com/ahmed-husssain)** | Digital library with session management and normalized relational schema | C# / MVC · Relational Database · Tailwind CSS | `SHIPPED` |

---

## What I Actually Built (Production C#)

```csharp
// 1. Idempotency — prevents duplicate transactions on double-click
var idempotencyKey = Request.Headers["X-Idempotency-Key"].ToString();
if (_memoryCache.TryGetValue(idempotencyKey, out object cached))
    return Json(cached);  // same response, zero duplicate processing

// 2. Optimistic concurrency — two collectors bid at the exact same millisecond
try { 
    await _context.SaveChangesAsync(); 
}
catch (DbUpdateConcurrencyException) {
    return Conflict(new { message = "Another bid committed right before yours. Please reload." });
}

// 3. Auction state reset — price integrity guard
if (product.Price > (existing.CurrentBid ?? 0)) {
    existing.CurrentBid = null; existing.HighestBidderId = null; existing.BidCount = 0;
}
```

---

## `dotnet build`

```text
  Ahmed -> bin/Release/net8.0/Ahmed.dll

  info  SHIFA     : clinical ERP in production, atomic billing locks, automated invoices
  info  GALLREX   : live auction engine, idempotent bids, OAuth 2.0, real users
  warn  APTECH25  : Runner-Up — Aptech Vision 2025 (Project: Mockrithm)
  info  STUDYING  : BSSE @ Virtual University · ACCP @ Aptech (Expected 2027)

Build succeeded.  0 errors.  1 award.  One stubborn love for clean schemas.
```

---

## Stack

<div align="center">

![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=dotnet&logoColor=white)
![ASP.NET Core](https://img.shields.io/badge/ASP.NET_Core-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![EF Core](https://img.shields.io/badge/EF_Core-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square&logo=microsoft&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat-square&logo=postman&logoColor=white)

</div>

```
backend/    C# · ASP.NET Core · Web API · EF Core · Concurrency Control · SQL Server · PostgreSQL
frontend/   React · TypeScript · Next.js · Tailwind CSS · Flutter · Riverpod
security/   OAuth 2.0 (Google · GitHub · Discord) · ASP.NET Identity · RBAC · JWT
tooling/    Visual Studio · Git · GitHub · Postman · Supabase
```

---

## `// stack trace of a career`

```text
at ShifaHealthcare.SoftwareDeveloper            (Karachi, Remote — Apr 2026 — Present)
   Clinical operations ERP, automated invoice dispatch, PostgreSQL row-level locks.

at Production.OnlineArtGallery                  (2025 — Present)
   Full e-commerce platform. Real auctions. Real OAuth. Concurrency conflict resolution.

at AptechVision.Mockrithm                       (2025)
   AI interview simulation. Runner-Up out of 50+ competing institutions across Karachi.

at Academic.Continuous_Learning                 (Ongoing — Expected 2027)
   BSSE @ Virtual University · ACCP @ Aptech. Building while studying.
```

---

<div align="center">

**[ahmedhusssain.vercel.app](https://ahmedhusssain.vercel.app/)** · **[ahmedhusssain.dev@gmail.com](mailto:ahmedhusssain.dev@gmail.com)** · **[LinkedIn](https://linkedin.com/in/ahmed-husssain)**

*If you read this far, the bid is idempotent. You can click hire twice. It's fine.*

</div>
