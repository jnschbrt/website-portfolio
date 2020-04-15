<template>
  <v-footer color="#313131" padless height="200" class="align-end">
    <v-row justify="center" no-gutters>
      <v-btn
        v-for="icon in icons"
        :key="icon.icon"
        class="mx-4 white--text"
        icon
        x-large
        :href="icon.link"
        target="_blank"
      >
        <v-icon size="24px">{{ icon.icon }}</v-icon>
      </v-btn>
      <v-col
        class="py-2 text-center white--text"
        justify="space-start"
        cols="12"
      >
        <div
          class="font-weight-light grey--text text--lighten-1 text-center"
          @click.stop="dialog = true"
        >
          Impressum / Datenschutz
        </div>

        <div class="font-weight-light grey--text text--lighten-1 text-center">
          &copy; {{ new Date().getFullYear() }} by Jonas Schubert — Made with
          <v-icon small class=" grey--text">mdi-heart-outline</v-icon>
          , a lot of
          <v-icon small class=" grey--text">mdi-coffee-outline</v-icon>
          and a bit
          <v-icon small class=" grey--text">mdi-vuetify</v-icon>
        </div>

        <v-dialog v-model="dialog" width="600px">
          <v-card>
            <v-card-title>
              <span class="headline black--text">Impressum</span>
            </v-card-title>
            <v-card-text>
              <p>Angaben gemäß § 5 TMG:</p>
              <p>
                <strong>Jonas Schubert</strong> <br />
                Weststraße 49 <br />
                48282 Emsdetten
              </p>
              <p class="font-weight-bold">Kontakt:</p>
              <p>
                E-Mail: info@jonas-schubert.eu <br />
                Mobil: 01520/2086954
              </p>
              <p class="font-weight-bold">Umsatzsteuer-ID:</p>
              <p>
                Umsatzsteuer-Identifikationsnummer gemäß §27a
                Umsatzsteuergesetz: <br />
                Als Kleinunternehmer im Sinne von §19 Abs. 1 Umsatzsteuergesetz
                (UStG) wird keine Umsatzsteuer berechnet
              </p>

              <p class="font-weight-bold">Cookies:</p>
              <p>
                Damit Sie unsere Webseite jederzeit leicht und ohne Verzögerung
                aufrufen können und damit wir unsere Angebote optimieren können,
                benutzen wir Cookies. Sie können der Zustimmung zur Nutzung von
                Cookies hier wiederrufen: <a>Zustimmung widerrufen</a>
              </p>
              <v-divider></v-divider>
              <br />
              <p class="headline black--text">Haftungsausschluss:</p>

              <p class="font-weight-bold">Urheberrecht:</p>
              <p>
                Die durch die Seitenbetreiber erstellten Inhalte und Werke auf
                diesen Seiten unterliegen dem deutschen Urheberrecht. Die
                Vervielfältigung, Bearbeitung, Verbreitung und jede Art der
                Verwertung außerhalb der Grenzen des Urheberrechtes bedürfen der
                schriftlichen Zustimmung des jeweiligen Autors bzw. Erstellers.
                Downloads und Kopien dieser Seite sind nur für den privaten,
                nicht kommerziellen Gebrauch gestattet. Soweit die Inhalte auf
                dieser Seite nicht vom Betreiber erstellt wurden, werden die
                Urheberrechte Dritter beachtet. Insbesondere werden Inhalte
                Dritter als solche gekennzeichnet. Sollten Sie trotzdem auf eine
                Urheberrechtsverletzung aufmerksam werden, bitten wir um einen
                entsprechenden Hinweis. Bei Bekanntwerden von Rechtsverletzungen
                werden wir derartige Inhalte umgehend entfernen.
              </p>

              <p class="font-weight-bold">Datenschutz:</p>
              <p>
                Die Nutzung unserer Webseite ist in der Regel ohne Angabe
                personenbezogener Daten möglich. Soweit auf unseren Seiten
                personenbezogene Daten (beispielsweise Name, Anschrift oder
                eMail-Adressen) erhoben werden, erfolgt dies, soweit möglich,
                stets auf freiwilliger Basis. Diese Daten werden ohne Ihre
                ausdrückliche Zustimmung nicht an Dritte weitergegeben. Wir
                weisen darauf hin, dass die Datenübertragung im Internet (z.B.
                bei der Kommunikation per E-Mail) Sicherheitslücken aufweisen
                kann. Ein lückenloser Schutz der Daten vor dem Zugriff durch
                Dritte ist nicht möglich. Der Nutzung von im Rahmen der
                Impressumspflicht veröffentlichten Kontaktdaten durch Dritte zur
                Übersendung von nicht ausdrücklich angeforderter Werbung und
                Informationsmaterialien wird hiermit ausdrücklich widersprochen.
                Die Betreiber der Seiten behalten sich ausdrücklich rechtliche
                Schritte im Falle der unverlangten Zusendung von
                Werbeinformationen, etwa durch Spam-Mails, vor. werden wir
                derartige Inhalte umgehend entfernen.
              </p>
              <p class="font-weight-bold">Google Analytics:</p>
              <p>
                Diese Website benutzt Google Analytics, einen Webanalysedienst
                der Google Inc. (''Google''). Google Analytics verwendet sog.
                ''Cookies'', Textdateien, die auf Ihrem Computer gespeichert
                werden und die eine Analyse der Benutzung der Website durch Sie
                ermöglicht. Die durch den Cookie erzeugten Informationen über
                Ihre Benutzung dieser Website (einschließlich Ihrer IP-Adresse)
                wird an einen Server von Google in den USA übertragen und dort
                gespeichert. Google wird diese Informationen benutzen, um Ihre
                Nutzung der Website auszuwerten, um Reports über die
                Websiteaktivitäten für die Websitebetreiber zusammenzustellen
                und um weitere mit der Websitenutzung und der Internetnutzung
                verbundene Dienstleistungen zu erbringen. Auch wird Google diese
                Informationen gegebenenfalls an Dritte übertragen, sofern dies
                gesetzlich vorgeschrieben oder soweit Dritte diese Daten im
                Auftrag von Google verarbeiten. Google wird in keinem Fall Ihre
                IP-Adresse mit anderen Daten der Google in Verbindung bringen.
                Sie können die Installation der Cookies durch eine entsprechende
                Einstellung Ihrer Browser Software verhindern; wir weisen Sie
                jedoch darauf hin, dass Sie in diesem Fall gegebenenfalls nicht
                sämtliche Funktionen dieser Website voll umfänglich nutzen
                können. Durch die Nutzung dieser Website erklären Sie sich mit
                der Bearbeitung der über Sie erhobenen Daten durch Google in der
                zuvor beschriebenen Art und Weise und zu dem zuvor benannten
                Zweck einverstanden.
              </p>
            </v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn text @click="dialog = false" color="#01d28e">
                Ok
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </v-col>
    </v-row>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    dialog: false,
    icons: [
      {
        icon: 'fab fa-github',
        link: 'https://github.com/Lizzal',
        tooltip: 'GitHub'
      },
      {
        icon: 'fab fa-twitter',
        link: 'https://twitter.com/_jnschbrt',
        tooltip: 'Twitter'
      },
      {
        icon: 'fab fa-xing',
        link: 'https://www.xing.com/profile/Jonas_Schubert10/cv',
        tooltip: 'XING'
      },
      {
        icon: 'fab fa-linkedin',
        link: 'https://www.linkedin.com/in/schubert-jonas',
        tooltip: 'LinkedIn'
      }
    ]
  })
}
</script>

<style></style>
