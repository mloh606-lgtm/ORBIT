# Orbit Team Organiser V3

This is the Netlify-ready, Supabase-connected pilot for up to five authorised team members.

## Live configuration
- **GitHub repository:** https://github.com/mloh606-lgtm/ORBIT
- **Netlify site:** https://unrivaled-concha-0ac9ab.netlify.app/
- **Supabase project:** https://supabase.com/dashboard/project/eqjhqcculoejgsfkosyo
- **Deploy:** root directory (\`netlify.toml\` specifies publish = "."), branch \"main\". No build command.
- **Client config:** \"orbit-config.js\" contains only the public Supabase URL and publishable key. Never commit service-role or secret keys.

## Connect the existing Netlify site to this GitHub repository

In the **existing** Netlify site, open **Project configuration → Developer settings → Continuous deployment → Repository → Link repository**. Select GitHub, authorise access to \`mloh606-lgtm/ORBIT\`, and use the \`main\` branch. This replaces manual file uploads with automatic deploys. Do **not** choose \"Push to new repository\", because the ORBIT repository already exists and contains the correct files.

The earlier Netlify deployment showed \"Dropped files\" and therefore did not deploy these GitHub files. After linking, check **Deploys** for a published deploy from the GitHub repository.

## Supabase setup and pilot access

The Orbit database has been installed, with restricted workspace access and revision-controlled writes. Existing auth users have not been allowlisted yet. To enable logins:

1. Confirm each tester's sign-in email in **Supabase → Authentication → Users**.
2. Add that lowercase address to \"public.orbit_allowed_emails\", using a unique \"member_slot\" from 1–5. One tester should have \"role\" = \"admin\"; other users can be \"member\". These roles are not yet separate permission tiers in this pilot.
3. In **Supabase → Authentication → URL Configuration**, set **Site URL** to https://unrivaled-concha-0ac9ab.netlify.app and add https://unrivaled-concha-0ac9ab.netlify.app/** as an allowed Redirect URL.
4. Test two different browser profiles to confirm that changes synchronize and that users cannot edit without signing in.

Do not enter live confidential customer data until the pilot has been tested with fictional records.
