# Contributing to TableRoom

Thank you for your interest in contributing! Here is everything you need to know.

## How to contribute

### Reporting bugs
Open an issue using the **Bug Report** template. Include as much detail as possible: steps to reproduce, expected vs actual behaviour, and your environment.

### Suggesting features
Open an issue using the **Feature Request** template. Describe the problem you are trying to solve and your proposed solution.

### Submitting code

1. **Fork** the repository and create a branch from `main`:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Set up** the project locally:
   ```bash
   cp .env.example .env
   # Fill in your credentials
   npm install
   cd server && npm install && cd ..
   cd client && npm install && cd ..
   npm run build
   npm run dev
   ```

3. **Make your changes** — keep them focused and minimal. One PR per feature or fix.

4. **Run the tests** before pushing:
   ```bash
   npm run test:all
   ```

5. **Open a Pull Request** against `main`. Fill in the PR template and link the related issue if there is one.

## Code style

- Follow the existing code conventions in the file you are editing.
- Do not add unnecessary comments or refactor code outside the scope of your change.
- Keep commits small and descriptive.

## Branch protection

The `main` and `sprint3` branches are protected. All changes must go through a Pull Request and require at least **1 approval** before merging.

## Contact

If you have any questions, open an issue or reach out at [picazosanchezmaria@gmail.com](mailto:picazosanchezmaria@gmail.com).
