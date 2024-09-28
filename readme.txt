url: https://project-planner-lr35.onrender.com/

1. interpolation/one-way binding
    -DA, src/components/Navbar.vue,  :3,:4 
2. two-way binding
    -DA, src/views/AddProject.vue,  :4, :6
3. methods
    -DA, src/views/HomeView.vue imamo handleDelete i handleComplete,   :29 - :37 
4. computed properties
    -NE
5. barem jedan scoped style
    - DA, src/components/SingleProject.vue koristi scoped style, :53
    - u src/views/HomeView.vue koristi stil koji na elemente h3 primjenjuje plavu boju, :43 - :46 
    - src/components/SingleProject.vue koristi stil koji na h3 elemente primjenjuje crnu boju,  :63 - :66
6. koristiti barem jedan lifecycle hook
    - DA,  src/views/HomeView.vue  koristi mounted() hook u kojoj dohvaća projekte s json-servera,  :23 - :28
7. routing (više stranica)-
    DA
    -dostupna - home stranica - https://project-planner-lr35.onrender.com/
              - add project stranica - https://project-planner-lr35.onrender.com/add
8. (barem) dvije komponente
    -DA
    - komponenta src/components/Navbar.vue - bez stanja
    - komponenta src/components/SingleProject.vue - sa stanjem
9. barem jedna komponenta mora emitirati barem jedan event
    -Da
    - komponenta src/components/SingleProject.vue emitira event pod imenom "delete", :34
    - događaj se emitira kada izbrišemo neku komponentu 
    - događajem "delete" signaliziramo roditeljskoj komponenti(src/views/HomeView.vue) da ažurira trenutne projekte
10. store (Pinia)
    - NE
11. asinkroni dohvat podataka s backenda, možete:
    DA
    - napravljen je json-server dostupan na https://fm-lab6-jsonserver.onrender.com/
    - na serveru su pohranjeni svi projekti u json formatu
    - za testiranje(npr s pomoću POSTMAN-a) moguće je koristi HTTP metode na https://fm-lab6-jsonserver.onrender.com/projects
    - u src/views/HomeView imamo moetdu fetch, :24
  