# C++/Python Project Template

This is a standardized C++/Python project template for DALSA projects that will be hosted on GitHub, designed to help project owners quickly set up new projects with a consistent structure and DevOps features. Its goal is to ensure maintainability and collaboration by enforcing standards that make future contributions and usage seamless. The template integrates **Sphinx** + **Doxygen** for unified documentation of both C++ and Python packages, and uses GitHub Actions to automate the generation of web-based documentation, code analysis (linting), code rewrites to follow a consistent style (formatting), and execution of tests.
This template introduces a certain structure so that users and contributors can quickly understand your project.

--- 

## Project Structure

    .
    ├── lib/               # Library for C++ and Python packages
    │   ├── cpp_pkg/       # C++ package
    │   └── py_pkg/        # Python package 
    ├── docs/              # Documentation built by Sphinx + Doxygen via Breathe
        ├── architecture/  # Component-based documentation
        ├── code/          # Code-based documentation
        └── usage/         # Examples and tutorials

All code is stored in `lib/` and organized into packages, either C++ or Python packages.\
All documentation, on the other hand, is stored in `docs/`. Documentation is a crucial aspect of this template. Using **Sphinx** with **Doxygen** via **Breathe**, code documentation is automated based on docstrings/comments and enriched with more info provided by the developers using **reStructuredText (reST)**. Together with GitHub Actions, this allows enforcement of consistent documentation practices across Python and C++ codebases. In this way:

*   Documentation stays up-to-date with code changes.
*   Documentation is organized and easily navigable.
*   A nice-looking and intuitive website is generated.
*   Both users and contributors can understand the codebase quickly.
*   The same standards are followed across different projects.

## Main Features

### Documentation Tools
- **Sphinx** — Primary tool for generating project documentation  
  - Supports both **reStructuredText (.rst)** and **Markdown (.md)** formats. 
  - Primarily uses reStructuredText, including its directives and extensions to produce documentation.

- **Doxygen** — Specialized for C++ code documentation  
  - Produces **HTML output** for standalone C++ docs (found in `docs/doxygen/html`).
  - Generates **XML output** used by **Breathe**, a bridge that lets **Sphinx** include C++ documentation.

### GitHub Actions
- **Linting**: Automatic linting (ruff for Python, clang-tidy for C++)  
- **Formatting**: Automatic styling (ruff format for Python, clang-format for C++)  
- **Documentation**: Automatic build and deployment to GitHub Pages  

## Before Using This Template
If you haven't done so already, check:  
- [Docs](/docs/) and learn how our project documentation is structured in `rst` and `md` files.
- [Lib](/lib/) and learn how to work with packages.
- [Docs Webpage](https://dalsa-lab.github.io/cpp_python_project_template/)

Do you think that's not enough? If not, then checking the following is highly recommended:
- [reStructuredText](https://www.sphinx-doc.org/en/master/usage/restructuredtext/index.html) (explore **reStructuredText Primer**, **Roles**, and **Directives**).
- [Sphinx Extensions](https://www.sphinx-doc.org/en/master/usage/extensions/index.html).
- [NumPy Style Guide](https://numpydoc.readthedocs.io/en/latest/format.html).
- [Doxygen Documenting Code Guide](https://www.doxygen.nl/manual/docblocks.html).
- Check [Clang-Tidy](https://clang.llvm.org/extra/clang-tidy/index.html) and [Clang-Format](https://clang.llvm.org/docs/ClangFormat.html).
- Check [Ruff](https://docs.astral.sh/ruff/).

## To Produce Documentation Locally: 
Assuming you are in the root directory of this project and have a Python envioment to work with:
1. Install Python dependencies:  
   ```bash
    pip install -r requirements-docs.txt
    doxygen Doxyfile # If there are any C++ packages
    sphinx-build -b html docs build/html
   ```

## License
This template is licensed under the terms in `LICENSE`.
