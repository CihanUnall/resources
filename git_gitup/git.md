## 1. Depo Başlatma ve Klonlama / Repository Initialization and Cloning / Repository-Initialisierung und Klonierung

#### • git init

    •Türkçe: Yeni bir Git deposu başlatır.
    •English: Initializes a new Git repository.
    •German: Initialisiert ein neues Git-Repository.

##### Örnek:

     git init

• Bu komut, bulunduğunuz dizinde yeni bir Git deposu oluşturur.

#### • git clone <repository-url>

        • Türkçe: Bir depoyu yeni bir dizine klonlar.

        • English: Clones a repository into a new directory.

        • German: Klont ein Repository in ein neues Verzeichnis.

##### Örnek:

    git clone https://github.com/user/repository.git

• Bu komut, belirtilen uzak depoyu klonlar ve yeni bir dizine kopyalar.

## 2. Değişiklikleri Kaydetme / Staging and Committing Changes / Änderungen Staging und Committen

#### • git add <file>

        ◦ Türkçe: Bir dosyadaki değişiklikleri bir sonraki commit için hazırlar.
        ◦ English: Stages changes to a file for the next commit.
        ◦ German: Fügt Änderungen an einer Datei für den nächsten Commit hinzu.

##### Örnek:

    git add index.html

• Bu komut, index.html dosyasındaki değişiklikleri bir sonraki commit için hazırlar.

#### • git commit -m "message"

         • Türkçe: Yapılan değişiklikleri commit eder. Commit mesajı, değişikliklerin ne olduğunu açıklar.
         • English: Commits staged changes with a message describing the changes.
         • German: Committet die gestagten Änderungen mit einer Nachricht, die die Änderungen beschreibt.

##### Örnek:

    git commit -m "Fixes the homepage layout"

• Bu komut, staging alanındaki değişiklikleri commit eder ve açıklama olarak "Fixes the homepage layout" mesajını kullanır.

#### • git commit --amend

         • Türkçe: Son yapılan commit’i değiştirir veya düzenler.
         • English: Edits or amends the most recent commit.
         • German: Ändert oder bearbeitet den letzten Commit.

##### Örnek:

     git commit --amend -m "Updated the homepage layout"

• Bu komut, son commit'i düzenler ve yeni mesaj olarak "Updated the homepage layout" kullanır.

## 3. Durum Kontrolü / Checking the Status / Überprüfung des Status

#### • git status

        ◦ Türkçe: Çalışma dizinindeki değişikliklerin durumunu gösterir.
        ◦ English: Displays the current status of the repository (staged, modified, untracked files).
        ◦ German: Zeigt den aktuellen Status des Repositories an (gestagte, modifizierte, nicht verfolgte Dateien).


##### Örnek:

    git status

• Bu komut, çalışma dizinindeki dosyaların durumunu gösterir (hangi dosyaların değiştirildiği, hangi dosyaların staging alanına eklendiği vb.).

#### • git diff

         • Türkçe: Değişikliklerin, çalışma dizini ile son commit arasındaki farklarını gösterir.
         • English: Shows the differences between the working directory and the last commit.
         • German: Zeigt die Unterschiede zwischen dem Arbeitsverzeichnis und dem letzten Commit an.

##### Örnek:

• git diff
• Bu komut, çalışma dizinindeki dosya değişikliklerini, son commit ile karşılaştırarak gösterir.

## 4. Dallanma ve Birleştirme / Branching and Merging / Verzweigung und Zusammenführung

#### • git branch

        ◦ Türkçe: Depodaki mevcut dalları listeler veya yeni bir dal oluşturur.
        ◦ English: Lists or creates branches in the repository.
        ◦ German: Listet oder erstellt Zweige im Repository.

##### Örnek:

    git branch

• Bu komut, mevcut dalları listeler.

#### • git checkout <branch>

        • Türkçe: Belirtilen dala geçiş yapar.
        • English: Switches to a specified branch in the repository.
        • German: Wechselt zu einem angegebenen Zweig im Repository.

##### Örnek:

     git checkout feature-xyz

• Bu komut, feature-xyz dalına geçiş yapar.

#### • git merge <branch>

         • Türkçe: Belirtilen dalı mevcut dal ile birleştirir.
         • English: Merges a specified branch into the current branch.
         • German: Führt einen angegebenen Zweig in den aktuellen Zweig zusammen.

##### Örnek:

    git merge feature-xyz

• Bu komut, feature-xyz dalını, şu anda aktif olan dala birleştirir.

## 5. Uzak Depolarla Çalışma / Working with Remote Repositories / Arbeiten mit Remote-Repositories

#### • git remote add <name> <url>

        ◦ Türkçe: Bir uzak depoyu, uzak depo listesine ekler.
        ◦ English: Adds a remote repository to the list of remotes.
        ◦ German: Fügt ein entferntes Repository zur Liste der Remotes hinzu.


##### Örnek:

     git remote add origin https://github.com/user/repository.git

• Bu komut, origin adıyla uzak bir depo ekler.

#### • git push

         • Türkçe: Yapılan commit'leri uzak depoya gönderir.
         • English: Pushes committed changes to a remote repository.
         • German: Überträgt die committeten Änderungen in ein entferntes Repository.

##### Örnek:

     git push origin main

• Bu komut, main dalındaki değişiklikleri uzak depoya gönderir.

#### • git pull

         • Türkçe: Uzak depodaki değişiklikleri alır ve yerel depo ile birleştirir.
         • English: Fetches and merges changes from a remote repository to your local repository.
         • German: Holt und fügt Änderungen aus einem entfernten Repository in dein lokales Repository ein.

##### Örnek:

     git pull origin main

• Bu komut, main dalındaki uzak değişiklikleri alır ve yerel depo ile birleştirir.

## 6. Geçmişi İnceleme / Viewing Commit History / Ansicht der Commit-Historie

#### • git log

        ◦ Türkçe: Commit geçmişini gösterir.
        ◦ English: Displays the commit history.
        ◦ German: Zeigt die Commit-Historie an.

##### Örnek:

    git log

• Bu komut, commit geçmişini gösterir ve her commit hakkında bilgi verir.

#### • git show <commit-id>

    • Türkçe: Belirli bir commit’in ayrıntılarını gösterir.
    • English: Shows details of a specific commit.
    • German: Zeigt Details eines bestimmten Commits an.

##### Örnek:

    git show abc123

• Bu komut, abc123 commit ID’sine ait ayrıntıları gösterir.

## 7. Değişikliklerden Geri Dönme / Undoing Changes / Änderungen Rückgängig Machen

#### • git reset <file>

        ◦ Türkçe: Bir dosyanın staging alanındaki değişikliklerini geri alır.
        ◦ English: Unstages a file, reverting it back to the last commit.
        ◦ German: Entfernt eine Datei aus dem Staging-Bereich und setzt sie auf den letzten Commit zurück.

##### Örnek:

     git reset index.html

• Bu komut, index.html dosyasını staging alanından geri alır.

#### • git reset --hard

    • Türkçe: Çalışma dizinindeki ve staging alanındaki tüm değişiklikleri geri alır, yani son commit’e döner.
    • English: Resets the working directory and staging area to the last commit, discarding changes.
    • German: Setzt das Arbeitsverzeichnis und den Staging-Bereich auf den letzten Commit zurück und verwirft Änderungen.

##### Örnek:

     git reset –hard

• Bu komut, çalışma dizinindeki tüm değişiklikleri geri alır ve son commit’e döner.

## 8. Etiketleme / Tagging / Tagging

#### • git tag <tag-name>

        ◦ Türkçe: Mevcut commit'e bir etiket (tag) ekler.
        ◦ English: Adds a tag to the current commit.
        ◦ German: Fügt dem aktuellen Commit ein Tag hinzu.

##### Örnek:

     git tag v1.0

• Bu komut, mevcut commit'e v1.0 etiketi ekler.

## 9. Uzak Depoya Bağlantı

#### • git fetch <remote>

           Türkçe: Uzak bir depodan en son değişiklikleri getirir ancak birleştirme yapmaz.
           English: Fetches changes from a remote repository but does not merge them.
           German: Holt Änderungen aus einem entfernten Repository, ohne sie zusammenzuführen.

##### Örnek:

     git fetch origin

• Bu komut, origin adlı uzak depodan tüm değişiklikleri çeker ancak yerel deponuzdaki dal ile birleştirme yapmaz.

#### • git push <remote> <branch>

           Türkçe: Yerel dalınızı, uzak depoya gönderir.
           English: Pushes your local branch to a remote repository.
           German: Überträgt deinen lokalen Zweig in ein entferntes Repository.

##### Örnek:

     git push origin master

• Bu komut, yerel master dalındaki değişiklikleri uzak depoya gönderir.

## 10. Uzak Depo Durumu Kontrolü

#### • git remote show <name>

           Türkçe: Uzak deponun ayrıntılı bilgilerini gösterir.
           English: Displays detailed information about a remote repository.
           German: Zeigt detaillierte Informationen zu einem entfernten Repository an.

##### Örnek:

     git remote show origin

• Bu komut, origin uzak deposunun URL'si, mevcut dallar, izlenen dallar gibi ayrıntıları gösterir.

#### • git ls-remote <repository>

Türkçe: Uzak depodaki referansları listeler.
English: Lists references from a remote repository.
German: Listet Referenzen aus einem entfernten Repository auf.

##### Örnek:

      git ls-remote origin

• Bu komut, uzak origin deposundaki referansları (dal adları ve etiketler) listeler.

## 11. Çakışma Çözümü ve Çakışma Durumunda İşlem Yapma

#### • Git çakışma durumu, birleştirme sırasında iki kişi aynı dosyanın aynı kısmını değiştirdiğinde oluşur.

            Türkçe: Bu durumda, dosyalar üzerinde manuel düzenleme yaparak çakışmayı çözmeniz gerekir.
            English: A conflict occurs when two people change the same part of a file during a merge. In this case, you need to manually resolve the conflict in the files.
            German: Ein Konflikt tritt auf, wenn zwei Personen während eines Merges denselben Teil einer Datei ändern. In diesem Fall müssen Sie den Konflikt manuell in den Dateien lösen.

#### • git merge <branch>

            Türkçe: Çakışma oluşturursa, dosyalar üzerinde manuel düzenleme yaparak çakışmayı çözmeniz gerekir.
            English: If a conflict occurs, you will need to manually resolve it by editing the files.
            German: Wenn ein Konflikt auftritt, müssen Sie ihn manuell durch Bearbeiten der Dateien lösen.

##### Örnek:

     git checkout master

##### Örnek:

     git merge feature

• Eğer bu birleştirme sırasında çakışmalar oluşursa, dosyalar üzerinde manuel düzenleme yaparak bu çakışmaları çözmeniz gerekir.

#### • git mergetool

            Türkçe: Çakışma çözmek için birleştirme aracını başlatır (bazı sistemlerde ek araçlar gerekebilir).
            English: Launches a merge tool to resolve conflicts (may require additional tools on some systems).
            German: Startet ein Merge-Tool zur Lösung von Konflikten (kann auf einigen Systemen zusätzliche Werkzeuge erfordern).

##### Örnek:

     git mergetool

• Bu komut, çakışmaları çözmek için birleştirme aracını başlatır. Eğer bilgisayarınızda birleştirme aracı kuruluysa, bu araçla çakışmaları çözebilirsiniz.
