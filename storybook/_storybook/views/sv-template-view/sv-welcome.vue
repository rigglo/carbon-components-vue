<template>
  <main class="welcome">
    <div class="welcome__hero">
      <h1 class="welcome__heading">
        <span class="nowrap">@rigglo/<span class="highlight">carbon-vue</span> </span>
      </h1>
    </div>
    <div class="welcome__info">
      <div class="bx--row">
        <div class="bx--no-gutter-md--left bx--offset-lg-2 bx--col-md-4 bx--col-lg-4">
          <a class="welcome__card" href="https://github.com/rigglo/carbon-components-vue">
            <div class="bx--aspect-ratio bx--aspect-ratio--2x1">
              <div class="bx--aspect-ratio--object">
                <div class="welcome__card-content">
                  <h5>Go to</h5>
                  <h4>the source repository</h4>
                  <div class="welcome__card-image">
                    <svg
                      focusable="false"
                      preserveAspectRatio="xMidYMid meet"
                      xmlns="http://www.w3.org/2000/svg"
                      width="32"
                      height="32"
                      viewBox="0 0 32 32"
                      aria-hidden="true"
                      class="MdxIcon-module--mdx-icon--3p_4x MdxIcon-module--icon-inverse--q6_WJ"
                    >
                      <path
                        fill="white"
                        fill-rule="evenodd"
                        d="M16 2a14 14 0 0 0-4.43 27.28c.7.13 1-.3 1-.67v-2.38c-3.89.84-4.71-1.88-4.71-1.88a3.71 3.71 0 0 0-1.62-2.05c-1.27-.86.1-.85.1-.85a2.94 2.94 0 0 1 2.14 1.45 3 3 0 0 0 4.08 1.16 2.93 2.93 0 0 1 .88-1.87c-3.1-.36-6.37-1.56-6.37-6.92a5.4 5.4 0 0 1 1.44-3.76 5 5 0 0 1 .14-3.7s1.17-.38 3.85 1.43a13.3 13.3 0 0 1 7 0c2.67-1.81 3.84-1.43 3.84-1.43a5 5 0 0 1 .14 3.7 5.4 5.4 0 0 1 1.44 3.76c0 5.38-3.27 6.56-6.39 6.91a3.33 3.33 0 0 1 .95 2.59v3.84c0 .46.25.81 1 .67A14 14 0 0 0 16 2z"
                      ></path>
                    </svg>
                  </div>

                  <div class="welcome__card-icon">
                    <svg
                      focusable="false"
                      preserveAspectRatio="xMidYMid meet"
                      aria-label="Open resource"
                      xmlns="http://www.w3.org/2000/svg"
                      width="20"
                      height="20"
                      viewBox="0 0 20 20"
                      role="img"
                    >
                      <path fill="white" d="M11.8 2.8l-1 1 5.4 5.5H1v1.4h15.2l-5.4 5.5 1 1L19 10z" />
                    </svg>
                  </div>
                </div>
              </div>
            </div>
          </a>
        </div>
        <!-- <div class="bx--no-gutter-md--left bx--col-md-4 bx--col-lg-4">
          <a class="welcome__card" href="https://carbon-components-vue-3.netlify.app/">
            <div class="bx--aspect-ratio bx--aspect-ratio--2x1">
              <div class="bx--aspect-ratio--object">
                <div class="welcome__card-content">
                  <h5>Take a look at our</h5>
                  <h4>Vue 3 version</h4>
                  <div class="welcome__card-image">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 196.32 170.02">
                      <path fill="#42b883" d="M120.83 0L98.16 39.26 75.49 0H0l98.16 170.02L196.32 0h-75.49z" />
                      <path fill="#35495e" d="M120.83 0L98.16 39.26 75.49 0H39.26l58.9 102.01L157.06 0h-36.23z" />
                    </svg>
                  </div>

                  <div class="welcome__card-icon">
                    <svg
                      focusable="false"
                      preserveAspectRatio="xMidYMid meet"
                      aria-label="Open resource"
                      xmlns="http://www.w3.org/2000/svg"
                      width="20"
                      height="20"
                      viewBox="0 0 20 20"
                      role="img"
                    >
                      <path fill="white" d="M11.8 2.8l-1 1 5.4 5.5H1v1.4h15.2l-5.4 5.5 1 1L19 10z" />
                    </svg>
                  </div>
                </div>
              </div>
            </div>
          </a>
        </div> -->
      </div>
    </div>
    <footer class="welcome__footer bx--grid">
      <div class="bx--row">
        <div class="welcome__footer-info bx--offset-lg-2 bx--col-sm-3 bx--col-md-4 bx--col-lg-4">
          <h3>Acknowledgement</h3>
          <p>
            A huge thank you to IBM for making Carbon Design System publicly available. This project is a fork of the
            original <a href="https://github.com/carbon-design-system/carbon-components-vue">@carbon/vue</a> package,
            and it would not be possible without the help of the many contributors of the original and other projects.
          </p>
          <h4>Thank you!</h4>
        </div>
      </div>
    </footer>
  </main>
</template>

<script>
import packageInfoRaw from '../../../../package-info';
const packageInfo = Object.values(packageInfoRaw).reduce((acc, line) => (line.type === 'inspect' ? line : acc), 0);

export default {
  name: 'SvWelcome',
  computed: {
    hasPackageInfo() {
      return !!packageInfo;
    },
    packageName() {
      return packageInfo.data.name;
    },
    packageLatest() {
      return packageInfo.data['dist-tags'].latest;
    },
    packageOtherTags() {
      const { latest, ...others } = packageInfo.data['dist-tags'];
      return others;
    },
    packageUpdated() {
      return new Date(packageInfo.data.time.modified).toLocaleDateString(undefined, {
        month: 'long',
        day: 'numeric',
        year: 'numeric',
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.welcome {
  min-height: 100vh;
  background-color: #fff;
  color: #000;
}

.welcome__hero {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-image: url('data:image/svg+xml;utf-8,<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 16 16" style="enable-background:new 0 0 16 16" xml:space="preserve"><rect x="0" y="0" fill="rgba(255, 255, 255, .35)" width="1" height="1"/></svg>');
  background-size: 16px;

  .highlight {
    font-weight: 600;
  }

  .nowrap {
    white-space: nowrap;
  }
}

.welcome__background-image {
  height: 300px;
  max-width: 60vw;
  padding: 30px 0;
}

.welcome__heading {
  font-size: 3.375rem;
  font-weight: 300;
  letter-spacing: 1px;
  padding: 0 20px 20px;
}

.welcome__info {
  padding: 1rem;
}

.welcome__card {
  display: block;
  margin: 20px 0;
  background-color: #262626;
  color: white;
  transition: background-color 70ms;

  &:hover {
    background-color: #393939;
  }

  .welcome__card-content {
    padding: 1rem 25% 1rem 1rem;
  }

  .welcome__card-icon {
    position: absolute;
    width: 20px;
    height: 20px;
    bottom: 1rem;
    right: 1rem;
  }

  .welcome__card-image {
    position: absolute;
    width: 32px;
    height: 32px;
    bottom: 1rem;
    left: 1rem;
  }
}

.welcome__footer {
  .welcome__footer-list-item {
    padding: 1px 0;
    a {
      color: #000;
      font-size: 0.875rem;
      font-weight: 400;
      line-height: 1.125rem;
      letter-spacing: 0.16px;

      &:not(:hover) {
        text-decoration: none;
      }
    }
  }

  .welcome__footer-info p,
  .welcome__footer-info ul {
    color: #000;
    font-size: 0.875rem;
    font-weight: 400;
    line-height: 1.125rem;
    text-decoration: none;
    letter-spacing: 0.16px;
    padding-bottom: 1rem;

    a {
      color: #000;
    }
  }

  .welcome__footer-logo {
    fill: #f4f4f4;
    margin: 2rem 0;
  }
}
</style>
