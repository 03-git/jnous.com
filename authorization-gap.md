title: Delegated Agent Authorization Gap
summary: Agents fail at auth boundaries, not capability boundaries. The blocker is infrastructure, not intelligence.
date: 2026-03-28
url: https://jnous.com/authorization-gap.md
source: production empirical
license: GPLv2


DELEGATED AGENT AUTHORIZATION GAP

RESULT

       When an agent fails to complete a delegated task, the failure
       is almost never capability. The agent knows what to do. It
       cannot authenticate to do it.

       GUI-only interfaces, OAuth browser redirects, MFA prompts,
       session tokens that require human presence — these are the
       actual blockers. The agent has the skill. The environment
       withholds the key.

IMPLICATION

       Capability investment (bigger models, better prompts, more
       context) does not fix authorization problems. Infrastructure
       investment does: API endpoints, programmatic auth, pre-auth
       keys, SSH.

       Question 2 from finding 01 ("what prevents the workflow from
       being autonomous?") surfaces this directly. The answer is
       rarely "the agent isn't smart enough." The answer is usually
       "the agent can't log in."

DATA
       raw.githubusercontent.com/03-git/variance-lab/refs/heads/main/findings/04-authorization-gap.txt
