<script lang="ts">

  type Node = {
    title: string;
    response: string;
    choices?: Node[];
  };


  const fixItYourself: Node = {
    title: "Fix it yourself",
    response: "You implement a cool page at this URL. It goes viral, bringing lots of new listeners to Syntax.",
    choices: [
      {
        title: "Get interviewed",
        response: "They interview you, but you dispute Syntax being a Canadian podcast and Wes (politely) kicks you off the show."
      },
      {
        title: "Buy some swag",
        response: "You buy some dope Syntax swag and wear it all the time, telling everyone about the awesome page you made."
      }
    ]
  }

  const createAnIssue: Node = {
    title: "Create an issue",
    response: "You create an issue asking people to fix it, but nobody knows what this page is supposed to be.",
    choices: [
      {
        title: "Make something up",
        response: "You confidently describe a page that never existed. Everyone takes it as fact and implements the page."
      },
      {
        title: "Close issue",
        response: "Maybe the real page was the friends we made along the way!"
      },
      fixItYourself
    ]
  }

  const questionNationality: Node = {
    title: "Question the nationality of the podcast",
    response: "Wes refuses to accept the reality that this is a global podcast.",
    choices: [
      {
        title: "Demand more proof",
        response: "Wes pulls up the Syntax website analytics showing that a small percentage of listeners are from Canada. 'Basically a Canadian podcast,' he declares triumphantly. Scott tries to explain percentages, but Wes is already moving on.",
        choices: [
          {
            title: "Ask Producer Randy to edit this conversation out",
            response: "Randy is editing timestamps for the 8267th episode. 'It's comedy gold, so it's staying in.' He adds a chapter marker: '34:22 - Wes Doubles Down on Canadian Thing Again.'"
          },
          {
            title: "Let CJ's bots decide the truth",
            response: "The comment section immediately fills with 'CJ wins' comments. Somehow this settles the debate. CJ's bots have spoken: CJ wins (again)."
          }
        ]
      },
      {
        title: "Give in",
        response: "You agree that it is a very Canadian podcast, but Scott bans you from listening to it again."
      }
    ]
  }

  const antiCjBots: Node = {
    title: "Create anti-CJ bots",
    response: "CJ realizes he's outmatched and disables his comment bots... for now..."
  }

  const askCjStopBots: Node = {
    title: "Ask him to stop",
    response: "Since Wes is a polite Canadian, you ask him to confront CJ about the bots, but CJ doesn't turn them off.",
    choices: [
      {
        title: "Try bribing the bots",
        response: "They ignore all offers except comments that say 'CJ wins'."
      },
      {
        title: "Add comment section moderation",
        response: "The bots evade the moderation by finding creative ways to spread their message"
      }
    ]
  }

  const sentryFixBots: Node = {
    title: "Ask Sentry to fix CJ's bots",
    response: "Sentry can't fix that! You'll have to fix the bots manually.",
    choices: [
      {
        title: "Get the whole Syntax crew together",
        response: "Wes, Scott, CJ, and Randy huddle around a monitor in an undisclosed. It's a team effort: Wes brings the Canadian optimism, Scott brings the Svelte knowledge, CJ brings the CSS minimizing skills, and Randy captures the whole thing on video. They fix everything in an hour."
      },
      {
        title: "Just let the bots win",
        response: "The bots continue commenting 'CJ wins' on everything. The metrics skyrocket. Engagement is through the roof. The 404 page gets so much traffic it becomes a landing page. CJ wins, and maybe that's okay."
      }
    ]
  }

  export const choices: Node[] = [
    {
      title: "Wes must've spilled maple syrup on the servers!",
      response: "Wes explains that he's using maple syrup as thermal paste for the CPUs to further solidify the Canadian culture of Syntax.",
      choices: [
        questionNationality,
        {
          title: "Call his phone and demand answers",
          response: "You try calling Wes, but his voice agent answers: I AM WINE SCHFAUR?"
        },
        {
          title: "Send him some real thermal paste",
          response: "You send Wes actual thermal paste, but the CPUs are already ruined!",
          choices: [
            {
              title: "Send him new CPUs",
              response: "Wes gladly accepts the CPUs, but he installs them while eating Poutine and spills cheese curds and gravy on them."
            },
            {
              title: "Cut off Wes' server access",
              response: "Wes protests, saying that the servers must be accessed by a Canadian since this is a Canadian podcast.",
              choices: [
                questionNationality,
                {
                  title: "Walk away shaking your head",
                  response: "Good idea, Wes can't be convinced otherwise. Scott sets up an American mirror of the site without the maple syrup, but this page still doesn't work :("
                }
              ]
            }
          ]
        },
      ]
    },
    {
      title: "Scott needs to stop refactoring everything",
      response: "You find Scott practicing his CSS battle skills.",
      choices: [
        {
          title: "Tell him to refactor less",
          response: "He challenges you to a CSS battle, and if he wins he can refactor as much as he wants.",
          choices: [
            {
              title: "Accept and battle him",
              response: "You do okay, but Scott uses an obscure single CSS property to easily win."
            },
            {
              title: "Accept, but cheat with AI",
              response: "You ask AI to compete for you, but it creates something totally wrong and you lose."
            },
            {
              title: "Tell him to battle Wes instead",
              response: "Scott and Wes agree to battle it out: Loser fixes the page.",
              choices: [
                {
                  title: "Easy Mode",
                  response: "You give them an easy challenge, and both of them complete it with the same exact code. Nobody loses, so nobody fixes the route :("
                },
                {
                  title: "Impossible Mode",
                  response: "Scott and Wes are stumped and both lose. They ask you to fix the page instead."
                }
              ]
            }
          ]
        },
        {
          title: "Ask him to fix it",
          response: "You ask him if he's able to take a look at the issue, but he's stuck at 99.99% on a CSS battle and can't do it right now",
          choices: [
            {
              title: "Help him get to 100%",
              response: "You work together and get the last few pixels aligned. Scott apologizes for refactoring and fixes the page, but later he refactors the codebase and breaks it again :("
            },
            {
              title: "Tell him to use SynHax instead",
              response: "He switches to SynHax and completes a challenge, then apologizes for refactoring and fixes the page. Later he refactors the codebase and breaks it again :("
            }
          ]
        },
        fixItYourself,
        {
          "title": "Ask Randy to produce a dramatic reconstruction of what happened",
          "response": "He starts narrating: “In a world where one link dared to break…”",
          "choices": [
            {
              "title": "Have Scott cameo as ‘The Refactorer’",
              "response": "Scott appears, declaring, “This code deserves justice,” and begins reorganizing files."
            },
            {
              "title": "Have Wes cameo as ‘The Canadian Oracle’",
              "response": "Wes enters foggy mist saying, “This is a Canadian podcast,” for absolutely no reason."
            },
            {
              "title": "Have CJ cameo as himself",
              "response": "CJ pops in, fixes a bug live, and his bots shout “CJ wins!” over the end credits."
            }
          ]
        }
      ]
    },
    {
      title: "CJ broke it while coding his comment bots",
      response: "You inspect the console logs and find thousands of automated comments that just say 'CJ wins' over and over. The bots have become sentient and are now competing for likes. This page was collateral damage.",
      choices: [
        {
          title: "Confront him",
          response: "CJ apologizes and agrees to make slightly less bot comments in the future, but this page doesn't get fixed.",
        },
        {
          title: "Hack to bots to say that Scott wins instead",
          response: "You change the bots to declare Scott the winner, but CJ quickly pulls the plug on them."
        },
        antiCjBots,
        askCjStopBots,
        sentryFixBots,
      ]
    },
    {
      title: "Blame it on the vibe coders",
      response: "Looks like someone was moving fast and breaking things, including this link!",
      choices: [
        {
          title: "Ask Sentry to fix it",
          response: "Sentry can't fix that!",
          choices: [
            {
              title: "Ask Scott to refactor the whole codebase",
              response: "Scott hears your plea and opens the project. Three weeks later, the 404 is fixed.",
              choices: [
                {
                  title: "Celebrate with some sick picks",
                  response: "Scott picks a water boiler. Wes picks a pizza cutter. All is well in the Syntax universe."
                },
                {
                  title: "Ask Scott to make a video showing what went wrong",
                  response: "The video goes viral! CJ's comment bots spam 'CJ Wins' even though CJ wasn't in the video",
                  choices: [
                    antiCjBots,
                    askCjStopBots,
                    sentryFixBots,
                  ]
                }
              ]
            },
            createAnIssue,
            fixItYourself
          ]
        },
        {
          title: "Ban AI in the codebase",
          response: "CJ writes a strongly worded addition to the README prohibiting PRs with AI generated code, but an AI hacks the repo and reverts it. This page is still a 404",
          choices: [
            createAnIssue,
            fixItYourself
          ]
        },
        {
          title: "Teach people to code better",
          response: "You tell people to simply go to Level Up Tuts and the Syntax YouTube channel and learn how to properly code, but this page is still a 404.",
          choices: [
            createAnIssue,
            fixItYourself
          ]
        }
      ]
    },
  ]

  let current: Node | null = $state(null);
  let trail: Node[] = $state([]);
  let highlighted = $state(0);
  let isDesktop = $state(true);


  let currentChoices = $derived.by(() => current !== null ? current.choices : choices)

  function pick(node: Node) {
    current = node;
    trail = [...trail, node];
    highlighted = 0;
  }

  function restart() {
    current = null;
    trail = [];
    highlighted = 0;
  }

  function goBack() {
    if (trail.length > 1) {
      trail = trail.slice(0, -1);
      current = trail[trail.length - 1];
      highlighted = 0;
    } else {
      restart();
    }
  }

  function handleKey(e: KeyboardEvent) {
    if (!isDesktop) return;

    const list = current ? current.choices ?? [] : choices;

    if (e.key === "ArrowDown") {
      highlighted = (highlighted + 1) % list.length;
    }
    if (e.key === "ArrowUp") {
      highlighted = (highlighted - 1 + list.length) % list.length;
    }
    if (e.key === "Enter") {
      pick(list[highlighted]);
    }
    if (e.key === "Backspace") {
      goBack();
    }
  }


  if (typeof window !== "undefined") {
    isDesktop = window.matchMedia("(pointer: fine)").matches;
    window.addEventListener("keydown", handleKey);
  }


  function typewriter(node: HTMLElement, params?: { duration?: number, delay?: number }) {
    // based on https://svelte.dev/docs/svelte/transition
    const valid = node.childNodes.length === 1 && node.childNodes[0].nodeType === Node.TEXT_NODE;

    if (!valid) {
      throw new Error(`This transition only works on elements with a single text node child`);
    }

    const text = node.textContent;

    return {
      delay: params?.delay ?? 0,
      duration: params?.duration ?? 300,
      tick: (t: any) => {
        const i = ~~(text.length * t);
        node.textContent = text.slice(0, i);
      }
    };
  }


</script>

<h2>Oops!</h2>
<ol>
    <li class="step-response" class:current={trail.length === 0} transition:typewriter|global>
        > You've landed on a page that doesn't exist!
    </li>

    {#each trail as step, i}
        <li class="step-title" in:typewriter|global={{
            delay: 100,
        }}>{step.title}</li>
        <li class="step-response" class:current={i === (trail.length - 1)} in:typewriter|global={{
                delay: 500,
            }}>> {step.response}</li>
    {/each}
</ol>

{#if currentChoices}
    <ul>
        {#each currentChoices as c, i (c.title)}
            <li>
                <button
                        class="choice"
                        onclick={() => { highlighted = i; pick(c); }}>
                    {c.title}
                </button>
            </li>
        {/each}
    </ul>
    <div class="choice-navigation">
        <button onclick={goBack} disabled={trail.length === 0}>Back</button>
    </div>
{:else}
    <div class="choice-navigation">
        <button onclick={goBack}>Back</button>
        <button onclick={restart}>Start Over</button>
    </div>
{/if}


<style>
    ul, ol {
        padding-left: 0;
    }

    li {
        list-style: none;
    }

    button.choice {
        white-space: nowrap;
        cursor: pointer;
        text-decoration: none;
        border: none;
        border-radius: 0;
        font-variation-settings: var(--fw-600);
        padding: 6px 15px;
        font-size: var(--body-font-size);
        background: none;
        width: auto;
        color: var(--fg);
        display: inline-flex;
        justify-content: center;
        align-items: center;
        gap: 10px;
        box-shadow: inset 0 0 0 var(--button-border-size) oklch(var(--blacklch) / 0.2);
        transition: background 0.2s ease-in-out;
    }

    button:disabled {
        opacity: 75%;
        pointer-events: none;
    }

    @media (pointer: fine) {
        .choice:hover {
            color: var(--yellow);
        }

        .choice:hover::before {
            content: '»';
            position: absolute;
            left: -.5rem;
        }
    }


    li {
        position: relative;
        padding-left: 0;
    }

    li + li {
        margin-top: 14px;
    }

    .step-title, .step-response {
        opacity: 80%;
        transition-property: opacity;
        line-height: 1.8rem;
    }

    .step-response {
        font-style: italic;
    }

    .step-response.current {
        opacity: 100%;
    }
</style>

