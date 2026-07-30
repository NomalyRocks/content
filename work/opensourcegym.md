---
order: 1
year: "2026"
code: OSS-01
placeholder: false
link: https://github.com/NomalyRocks/OpenSourceGym
stack: [TypeScript, Express, MongoDB, Redis, React Native, WebSocket, ESP32]
en:
  name: OpenSourceGym
  summary: >-
    A self-hosted gym access system: the member scans the QR taped to the
    turnstile, and the same app tells them how many days of membership are left.
  client: Open source, self-initiated
  role: Product definition, architecture, full-stack and device firmware
  tags: [Open source, Access control]
  challenge: >-
    Turnstile automation is sold as a monthly licence with an installation fee
    attached. A gym that cannot carry that cost runs entry control from a
    notebook at the desk: no record of who came in, and no way to separate a
    lapsed membership from a current one without asking.
  solution: >-
    The scan is inverted. The QR code is static and lives on the turnstile; the
    phone is what reads it. No relay fires until the backend has checked the
    subscription, the phone's GPS against the gym's coordinates, and whether the
    gate agent is still connected — and it fails closed, so a dropped socket
    never leaves a turnstile open. Memberships, staff roles, and every
    subscription change pass through one audited API, with reference gate agents
    for Raspberry Pi and ESP32.
  result: >-
    Everything through account-sharing detection is built and every line of it
    is public: QR entry, live occupancy from the gate counters, TOTP and email
    MFA on sensitive actions, KVKK consent and deletion flows. A gym can read
    the code, host it themselves, and owe no licence for it. What it is not yet
    is field-proven — it has been verified end to end in development, not across
    a season of real turnstile traffic.
tr:
  name: OpenSourceGym
  summary: >-
    Kendi sunucunuzda çalışan spor salonu geçiş sistemi: üye turnikeye
    yapıştırılmış QR'ı okutup geçiyor, aynı uygulamada üyeliğinden kaç gün
    kaldığını görüyor.
  client: Açık kaynak, kendi girişimimiz
  role: Ürün tanımı, mimari, full-stack ve cihaz yazılımı
  tags: [Açık kaynak, Geçiş kontrolü]
  challenge: >-
    Turnike otomasyonu, üzerine kurulum bedeli eklenmiş aylık lisansla
    satılıyor. Bu maliyeti kaldıramayan salon giriş kontrolünü resepsiyondaki
    deftere yazarak yürütüyor: kimin ne zaman girdiğinin kaydı yok, biten
    üyelikle devam edeni sormadan ayırmanın yolu yok.
  solution: >-
    Okutma yönü tersine çevrildi. QR statik ve turnikenin üzerinde duruyor,
    okutan taraf üyenin telefonu. Backend aboneliği, telefonun GPS konumunu
    salon koordinatlarıyla ve turnike agent'ının bağlı olup olmadığını
    doğrulamadan röleye komut gitmiyor — bağlantı koptuğunda sistem kapalı
    tarafa düşüyor, turnike açık kalmıyor. Üyelik, personel rolleri ve her
    abonelik işlemi denetim kaydı tutan tek bir API'den geçiyor; turnike
    tarafında Raspberry Pi ve ESP32 için referans agent'lar var.
  result: >-
    Hesap paylaşımı tespitine kadar olan her şey tamamlandı ve tamamı açık: QR
    ile geçiş, turnike sayaçlarından anlık doluluk, hassas işlemlerde TOTP ve
    e-posta MFA, KVKK aydınlatma ve silme akışları. Salon kodu okuyabilir, kendi
    sunucusuna kurabilir, lisans ödemez. Henüz sahada kanıtlanmış değil — uçtan
    uca geliştirme ortamında doğrulandı, bir sezonluk gerçek turnike
    trafiğiyle değil.
---
