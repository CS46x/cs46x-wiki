_Owner: Team | Last updated: 2026-02-19 | Status: Draft_

# GenAI Usage Log & Citations

## Purpose
How AI was used, prompts/summaries, and attributions (matches course policy).

## Entry template
- **Date:** 2026-02-19
- **Owner:** @TalatAli
- **Purpose:** Validate frontend password reset flow against backend ASP.NET controller and model.
- **Prompt/input (summary):** Provided account-recovery component, backend AccountController confirm-reset method, and associated reset models. Asked whether frontend payload matched backend model and which fields were required (token vs passcode, email required, confirm password required).
- **Output (summary):** Identified field mismatches and naming inconsistencies between frontend request body and backend ConfirmPasswordResetModel. Clarified required properties and alignment needed for successful model binding.
- **Where applied:** 
account-recovery-form.component.ts
Password reset confirm API call
ConfirmPasswordResetModel.cs
- **Verification:** Manually validated against backend controller method and inspected browser network payload to confirm model binding and HTTP response behavior.
- **Attribution/citations:** Analysis assisted by OpenAI ChatGPT. Final validation performed manually in controller and browser DevTools.

---

- **Date:** 2026-01-27
- **Owner:** @adamb
- **Purpose:** Learn Angular syntax, patterns, and concepts as someone with a React background working with an Angular app.
- **Prompt/input (summary):** Described prior React experience and asked for explanations of Angular concepts encountered while reading the  codebase: component structure and decorators (`@Component`, `@Input`, `@Output`), Angular services and dependency injection, `NgModule` vs standalone components, template syntax (`*ngIf`, `*ngFor`, `[(ngModel)]`), reactive forms vs template-driven forms, Angular Signals (`signal()`, `computed()`, `effect()`), `Observable` and RxJS operators as used in Angular (vs React's `useEffect`/`useState`), and the Angular router.
- **Output (summary):** Received explanations comparing each Angular concept to its React equivalent where applicable. Helped build a working mental model for reading and writing Angular components and services.
- **Where applied:** General day-to-day frontend development across all Angular components and services worked on.
- **Verification:** Cross-referenced explanations against the Angular documentation and the existing code written by the original app author.
- **Attribution/citations:** Explanation and learning assistance provided by OpenAI ChatGPT. All implementation written manually.

