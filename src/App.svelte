<script>
  // Importer les dépendances nécessaires
  import svelteLogo from './assets/svelte.svg';
  import viteLogo from '/vite.svg';
  import QuestionCard from './QuestionCard.svelte'; // Vous devrez créer ce composant

  // Données pour les questions et réponses
  let questions = [
    {
      id: 1,
      number: 'Question 1',
      title: 'Votre entreprise a décidé d’acquérir une solution SaaS pour sonportail de statistiques auprès d’un éditeur et vous devez rédiger dans l’appel d’offre la partie sur les exigences techniques en termes de sobriété numérique.\n' +
        'Listez les critères qui vous semblent non négociables sous forme de user stories fictives.',
      content: `
        <div class="user-story"><b>User Story 1 :</b> En tant qu'éditeur, je dois garantir une intégration parfaite avec les systèmes existants chez 24S pour assurer une transition fluide et sécurisée.</div>
        <div class="development">Ceci implique une compatibilité technique avec les plateformes de commerce électronique et les bases de données de clients haut de gamme utilisées chez 24S.</div>
        <div class="user-story"><b>User Story 2 :</b> En tant qu'éditeur, je dois fournir des outils d'analyse de données avancés pour permettre à 24S de personnaliser les expériences clients.</div>
        <div class="development">Cela nécessite des capacités de traitement et d'analyse des données en temps réel pour offrir des insights précis sur les comportements des consommateurs.</div>
        <div class="user-story"><b>User Story 3 :</b> La solution doit respecter les normes environnementales les plus élevées, conformément à l'engagement de LVMH en faveur de la durabilité.</div>
        <div class="development">Cela implique l'utilisation de centres de données verts et la mise en œuvre de pratiques visant à minimiser l'empreinte écologique de la solution.</div>
        <div class="user-story"><b>User Story 4 :</b> En tant qu'éditeur, je dois assurer une haute disponibilité et une résilience du système, essentielles pour le commerce en ligne de luxe.</div>
        <div class="development">Cela signifie maintenir une infrastructure robuste et des plans de secours pour garantir une expérience client ininterrompue.</div>
        <div class="user-story"><b>User Story 5 :</b> Je dois fournir une solution hautement évolutive pour accompagner la croissance et l'expansion internationale de 24S.</div>
        <div class="development">La solution doit pouvoir s'adapter facilement à un volume croissant de transactions et à une clientèle mondiale.</div>
        `,
      isOpen: false,
    },
    {
      id: 2,
      number: 'Question 2',
      title: 'Quels éléments du cours allez-vous utiliser dans votre alternance (pour les personnes qui ont trouvé) et/ou votre vie étudiante(pour les personnes en recherche) ?',
      content: `
        <div class="element"><b>Intégration de l'intelligence artificielle :</b> Utilisation de l'IA pour améliorer la personnalisation des services et l'expérience client chez 24S, en cohérence avec la stratégie numérique de LVMH.</div>
        <div class="element"><b>Focus sur la sécurité des données :</b> Renforcer la sécurité des données dans tous les développements, en reconnaissant l'importance de la confidentialité des données pour les clients de luxe.</div>
        <div class="element"><b>Optimisation des performances :</b> Appliquer des stratégies pour améliorer l'efficacité des systèmes back-end, réduisant ainsi les coûts et l'impact environnemental.</div>
        <div class="element"><b>Approches centrées sur l'utilisateur :</b> Développer des solutions mettant l'accent sur l'expérience utilisateur, essentielle dans le secteur du luxe.</div>
        `,
      isOpen: false,
    },
    {
      id: 3,
      number: 'Question 3',
      title: 'Comment évaluez-vous la maturité de sobriété numérique de votre organisation? (ou d’une autre organisation si pas encore d’alternance). Détaillez les actions déjà mises en œuvre et ce qu’il faudrait selon vous améliorer.',
      content: `
        <div class="title-element"><b>Actions Mises en Œuvre :</b></div>
        <div class="element"><b>Infrastructure Cloud éco-responsable :</b> Utilisation de solutions cloud énergétiquement efficaces et alimentées par des énergies renouvelables, alignées avec les objectifs de durabilité du groupe LVMH.</div>
        <div class="element"><b>Stratégies de réduction des déchets numériques :</b> Implémentation de politiques visant à minimiser les déchets électroniques, y compris le recyclage et la réutilisation des équipements informatiques.</div>
        <div class="element"><b>Programmes de sensibilisation à l'environnement :</b> Organisation régulière de sessions de formation pour sensibiliser les employés aux impacts environnementaux du numérique et encourager les pratiques durables.</div>

        <div class="title-element"><b>Améliorations Nécessaires :</b></div>
        <div class="element"><b>Renforcement de l'écoconception :</b> Intégrer davantage de principes d'écoconception dans le développement de nouveaux produits et services numériques, réduisant ainsi l'empreinte écologique.</div>
        <div class="element"><b>Optimisation des processus IT :</b> Examiner et améliorer les processus informatiques pour augmenter l'efficacité énergétique et réduire la consommation de ressources.</div>
        <div class="element"><b>Adoption accrue de technologies durables :</b> Explorer des solutions technologiques innovantes pour réduire davantage l'impact environnemental, telles que l'IA pour optimiser l'utilisation des ressources.</div>
    `,
      isOpen: false,
    },
    {
      id: 4,
      number: 'Question 4',
      title: 'Comment imaginez-vous le numérique en 2050?',
      content: `
        <div class="element"><b>Innovations numériques dans le luxe :</b> Utilisation de technologies avancées pour enrichir l'expérience client dans le luxe.</div>
        <div class="element"><b>Engagement envers la durabilité :</b> Focus continu sur le développement de solutions numériques durables.</div>
        <div class="element"><b>Développement de produits personnalisés :</b> Création de produits et services de luxe hautement personnalisés grâce au numérique.</div>
        <div class="element"><b>Expériences immersives :</b> Intégration de la réalité augmentée et virtuelle pour proposer des expériences d'achat uniques.</div>
        <div class="element"><b>Commerce électronique intégré :</b> Développement continu du commerce en ligne pour répondre aux attentes des clients de luxe.</div>
        `,
      isOpen: false,
    },
  ];

  // Fonction pour basculer l'état ouvert/fermé de la carte
  function toggleQuestion(id) {
    questions = questions.map(q =>
      q.id === id ? {...q, isOpen: !q.isOpen} : q,
    );
  }

</script>
<div class="background-container">
    <div class="background"></div>
    <div class="container">
        {#each questions as question}
            <QuestionCard
                    key={question.id}
                    question={question}
                    onToggle={() => toggleQuestion(question.id)}
            />
        {/each}
        <h2>Réalisé avec Vite et Svelte</h2>
        <div>
            <a href="https://vitejs.dev" target="_blank" rel="noreferrer">
                <img src={viteLogo} class="logo" alt="Vite Logo"/>
            </a>
            <a href="https://svelte.dev" target="_blank" rel="noreferrer">
                <img src={svelteLogo} class="logo svelte" alt="Svelte Logo"/>
            </a>
        </div>
        <p>
                        <strong>M1PEX DD</strong> par <a>Hugo Da Silva.</a> M1PEX 2023-2024 - Efrei Villejuif, 94076.
                    </p>
    </div>
</div>
